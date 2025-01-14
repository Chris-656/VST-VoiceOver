# Installing
This workflow gives exact commands how to clone a voice using piper locally. NVideo card is necessary.

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
Define an folder where the vpoice samples are defined. The format must be like this.

![image](https://github.com/user-attachments/assets/20024ba6-2f71-41d4-a5f4-c77b102d13f6)

Structure of the template metadate.csv file 

```
4000000001_4000000300_CustomerService/4000000022.wav|We're deeply sorry about that.
4000000001_4000000300_CustomerService/4000000026.wav|Let me check and see what I can do for you.
4000000001_4000000300_CustomerService/4000000035.wav|Would you like to speak with a supervisor?
4000000001_4000000300_CustomerService/4000000004.wav|Thank you so much, you too!
```

```
cp -r /mnt/d/AItranslate/Input/michi ~/piper/datasets
mkdir -p ~/piper/my-training
```
# Preprocess
```
cd ~/piper/src/python/

python3 -m piper_train.preprocess \
  --language en \
  --input-dir ~/piper/datasets \
  --output-dir ~/piper/my-training \
  --dataset-format ljspeech \
  --single-speaker \
  --sample-rate 22050
```

# Training
## Ryan
getting RYAn medium prelearned data in order to fine tune on specific training voice data
```
wget https://huggingface.co/datasets/rhasspy/piper-checkpoints/resolve/main/en/en_US/ryan/medium/epoch%3D4641-step%3D3104302.ckpt -O ~/piper/epoch=4641-step=3104302.ckpt

```

```
cd ~/piper/src/python/

python3 -m piper_train \
    --dataset-dir ~/piper/my-training \
    --accelerator 'gpu' \
    --devices 1 \
    --batch-size 12 \
    --validation-split 0.0 \
    --num-test-examples 0 \
    --max_epochs 6000 \
    --resume_from_checkpoint ~/piper/epoch=4641-step=3104302.ckpt \
    --checkpoint-epochs 1 \
    --precision 32
```

# Exporting
```
mkdir ~/piper/my-model

python3 -m piper_train.export_onnx \
    ~/piper/my-training/lightning_logs/version_0/checkpoints/epoch=5589-step=1382940.ckpt \
    ~/piper/my-model/model.onnx
    
cp ~/piper/my-training/config.json \
   ~/piper/my-model/model.onnx.json
```
