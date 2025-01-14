# Installing
This workflow gives exact commands how to clone a voice using piper locally. NVideo card is necessary. I used the workflow from "https://ssamjh.nz/create-custom-piper-tts-voice/" and adpated it for my use.

## using wsl 
```
$wsl -d Ubuntu-20.04
```
oder Neuinstallation

```
$wsl -install -d Ubuntu-20.04
```

```
sudo apt update
sudo apt dist-upgrade -y
sudo apt install python3-dev python3.10-venv espeak-ng ffmpeg build-essential -y
```


Starting installing packages
```
cd ~/
git clone https://github.com/rhasspy/piper.git
python3 -m venv ~/piper/src/python/.venv

cd ~/piper/src/python/
source ~/piper/src/python/.venv/bin/activate

#python3 -m pip install --upgrade pip
python3 -m pip install piper-tts     (new worked for me)
python3 -m pip install --upgrade wheel setuptools
python3 -m pip install -e .
sudo bash ~/piper/src/python/build_monotonic_align.sh

python3 -m pip install torchmetrics==0.11.4

pip install numpy==1.26.4    // since numpy 2-02 is not working in this workflow
pip install torch==1.11.0+cu113 torchvision==0.12.0+cu113 torchaudio==0.11.0 --extra-index-url https://download.pytorch.org/whl/cu113

```
# Data Preparation and Copying
Define a folder where the voice samples are defined. You can use piper Recording Studio (https://github.com/rhasspy/piper-recording-studio)  to record your voice. Use at least 200 samples. 
The format must be like this.

![image](https://github.com/user-attachments/assets/20024ba6-2f71-41d4-a5f4-c77b102d13f6)

Structure of the template metadate.csv file 

```
4000000001_4000000300_CustomerService/4000000022.wav|We're deeply sorry about that.
4000000001_4000000300_CustomerService/4000000026.wav|Let me check and see what I can do for you.
4000000001_4000000300_CustomerService/4000000035.wav|Would you like to speak with a supervisor?
4000000001_4000000300_CustomerService/4000000004.wav|Thank you so much, you too!
```

```
cp -r /mnt/d/AItranslate/Input/chris2 ~/piper/datasets
mkdir -p ~/piper/my-training
```

# Definitions used during the training
The following path and name of files are defined here for the entire process

```
model_name="chris2"
input_dir="~/piper/$model_name/input"
output_dir="~/piper/$model_name/training"
model_dir="~/piper/$model_name/model"
lastepoch_dir="~/piper/$model_name

mkdir -p $model_dir
mkdir -p $output_dir
mkdir -p $model_dir

```
## Ryan
getting RYAn medium pre-learned data in order to fine tune on specific training voice data
```
wget https://huggingface.co/datasets/rhasspy/piper-checkpoints/resolve/main/en/en_US/ryan/medium/epoch%3D4641-step%3D3104302.ckpt -O  $lastepoch_dir/epoch=4641-step=3104302.ckpt

```
# Preprocess
```
cd ~/piper/src/python/

python3 -m piper_train.preprocess \
  --language en \
  --input-dir $input_dir \
  --output-dir $training_dir \
  --dataset-format ljspeech \
  --single-speaker \
  --sample-rate 22050
```

# Training

```
cd ~/piper/src/python/

python3 -m piper_train \
    --dataset-dir $training_dir \
    --accelerator 'gpu' \
    --devices 1 \
    --batch-size 12 \
    --validation-split 0.0 \
    --num-test-examples 0 \
    --max_epochs 5000 \
    --resume_from_checkpoint $lastepoch_dir/epoch=4641-step=3104302.ckpt \
    --checkpoint-epochs 1 \
    --precision 32
```

# Exporting
This command creates the onnx files to be used in piper or subtitleedit.

```
last_epoch="$training_dir/lightning_logs/version_0/checkpoints/epoch=5589-step=1382940.ckpt"  // define the checkpoint from the training

python3 -m piper_train.export_onnx \
   $last_epoch \
   model_dir/model.onnx
    
cp $training_dir/config.json  $model_dir/model.onnx.json
```
