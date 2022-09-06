# 🚗 Driver-Drowsiness-Detection 🚗
A Driver Drowsiness Detection project that was created using YOLOv5, PyTorch and Roboflow which ran on NVIDIA® Jetson Nano™ by detecting whether the driver is drowsy or not based on his/her eyes that are either open or closed.

# Required Hardware 
1. NVIDIA® Jetson Nano™ 
2. Logitech C270 HD Webcam (recommended)

# Dataset Preparation 
All dataset were collected locally and are of original images. [Roboflow](https://roboflow.com/), a website to annotate the images.
2 classes were annotated which were; Open Eyes and Closed Eyes. Dataset was then uploaded to Google Drive.

# Model Creation
[Model](https://colab.research.google.com/drive/1tXKlUt1uDqrg5XhFfyBRrxSUL2r9S8pA#scrollTo=kfU0Mn2S_4V_) was built and trained using [Google Colab](https://colab.research.google.com/)

Quick tip: Make sure you change Runtime to GPU to accelerate processes (Runtime > Change runtime type > Hardware accelerator > GPU)

custom.yaml was created to create a script to pass through the train and validation dataset

best.pt is then saved, renamed to driver.pt and placed in the yolov5 directory later on 

# Configuring NVIDIA® Jetson Nano™ (Using Terminal)
It is crucial to install all required libraries needed to run the program.

# Creating a new environment with Python Version 3.8
```
conda create -n myenv python=3.8
```
[Environment Guide](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#viewing-a-list-of-your-environments)

# Installing Necessary Libraries/Framework 

1. Cloning the YoloV5 repo 
```
git clone https://github.com/ultralytics/yolov5
```
```
cd yolov5
```
```
pip install -r requirements.txt
```

2. Modify requirements.txt

-Locate and open YoloV5 directory

-Open requirements.txt using text editor (Notepad)

-Change these commands into comment: #torch>=1.7.0 and #torchvision>=0.8.1

3. Installing PyTorch (This will take a while)
```
git clone --recursive --branch 1.7 http://github.com/pytorch/pytorch
```
```
cd pytorch
```
```
python3.8 -m pip install -r requirements.txt
```
```
python3.8 setup.py install
```

4. Installing torchvision 
```
git clone https://github.com/pytorch/vision
```
```
cd vision/
```
```
git checkout v0.8.
```
```
python3 setup.py bdist_wheel
```
```
python3 -m pip install dist/torchvision-0.8.0a0+291f7e2-cp38-cp38-linux_aarch64.whl
```

# Checking GPU
-Change directory back to HOME and then:
```
python 3
```
```
import torch
```
```
torch.cuda.is_available()
```
```
torch.cuda.current_device()
```
```
torch.cuda.device(0)
```
```
torch.cuda.device_count()
```
```
torch.cuda.get_device_name(0)
```

# Running the Inference through the Webcam 

```
source activate newenv #Activate the previously created Python Version 3.8 environment
```
```
cd yolov5 
```
```
python detect.py --weights driver.pt --source 0 #Run inference using webcam
```

# Thank you 🌹
Thanks to everyone who helped me build the project, including the lecturers, facilitators, friends, and family. Feel free to contact me through my [email](mailto:zainihazeeq@gmail.com).
