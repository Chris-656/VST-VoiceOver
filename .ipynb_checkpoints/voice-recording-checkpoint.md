# Piper – Recording Studio
I used the workflow from https://ssamjh.nz/  and adpted a few things.

Creating the venv
Piper Recording Studio allows us to easily record a dataset to train a model of our voice with.

## Install:
```
cd ~/

git clone https://github.com/rhasspy/piper-recording-studio.git

python3 -m venv ~/piper-recording-studio/.venv

cd ~/piper-recording-studio/
source ~/piper-recording-studio/.venv/bin/activate

python3 -m pip install --upgrade pip
python3 -m pip install -r requirements.txt
python3 -m pip install -r requirements_export.txt
```
Run:
```
python3 -m piper_recording_studio
```
## Recording
Go to http://localhost:8000, and follow the steps.
I used the English (United Kingdom) option. It best matches the New Zealand accent, but pick one that works best for you.

In my testing, I’ve done at least 200, but for the best results you should train as many as possible.


## Exporting
Once you’re happy with the recordings, you can quit the program by pressing Ctrl + C.

Replace <lang> with your recording language. Identify it by checking the output directory or the URL during recording (http://127.0.0.1:8000/record?language=en-GB)

Exporting:
```
python3 -m export_dataset output/<lang>/ ~/piper-recording-studio/my-dataset
```
Finishing up:
```
deactivate
```
