# CS3244-ML-Project
Blind people voice guide app
<br/>Created by National University of Singapore CS3244 Machine Learning Group 25 and 26. All of us are equally contributed.
<br/>[Jin Shuyuan](https://github.com/CoderStellaJ), [Mou Ziyang](https://github.com/mouziyanglovestudy), [Tian Xin](https://github.com/tianxin9628), [Tian Xueyan](https://github.com/xueyantian), [Wang Tengda](https://github.com/JacobWangTengda), [Zhao Tianze](https://github.com/tankztz)

### 1. App features
- GPS location share 
  <br/>location is shared to family to ensure blind people's safety in case of emergency.
- Camera based image capturing 
  <br/>capture real-time view in front of the user.
- Object detection and classification
  <br/>focus on human object
- Moving direction determination
  <br/>based on bounding box size in sequencial images to determine whether the peron is moving to/away from the user.
- Voice Guide
  <br/>based on object classification and moving direction, output audio guide (a person is moving to you/ a person is moving away from you)
  
  
### 2. Research on dataset and [neural network](https://towardsdatascience.com/r-cnn-fast-r-cnn-faster-r-cnn-yolo-object-detection-algorithms-36d53571365e) (4.1 ~ 4.2)

Neural Network |NN Link| Description | Paper
--- | --- | ---| --- |
YOLOv3 |https://pjreddie.com/darknet/yolo/    https://github.com/AlexeyAB/darknet  (for both windows and linux) |YOLO is a state-of-the-art, real-time object detection system. It has Pretrained Convolutional Weights which is tarined on Imagenet. | https://pjreddie.com/media/files/papers/yolo.pdf |
Faster R-CNN  |https://github.com/ShaoqingRen/faster_rcnn| |https://papers.nips.cc/paper/5638-faster-r-cnn-towards-real-time-object-detection-with-region-proposal-networks.pdf | 

![github-small](https://github.com/CoderStellaJ/CS3244-ML-Project/blob/master/Baselines.PNG)

Dataset| Link| Description |
---|---|---|
ImageNet | http://www.image-net.org/ |  |
COCO dataset|http://cocodataset.org/#home ||
Pascal VOC challenge|http://host.robots.ox.ac.uk/pascal/VOC/index.html| |

### 3. Detailed instructions for setting up YOLOv3(4.3 ~ 4.6)

The official [YOLOv3](https://pjreddie.com/darknet/yolo/) is implemented using C language on Linux OS. For our convenience, a simplified [pytorch version](https://github.com/ultralytics/yolov3) is used for this project. And some useful parts of the code has been copied and uploaded in this repository.

- Make sure your laptop has Python installed. Anaconda is recommended for installing Python as it helps to install various dependencies.
- Run the following commands using Git Bash
```
    $ git clone https://github.com/CoderStellaJ/CS3244-ML-Project.git
    $ cd CS3244-ML-Project/
```
- Download pretrained weights
<br/> The pretrained weights can be downloaded [here](https://pjreddie.com/media/files/yolov3.weights) which is trained on COCO dataset
<br/> Then, copy the weights into ```.\weights```

- Obtain COCO dataset
<br/> Due to space constraints of our laptop, for testing, we currently don't need to download the whole dataset
<br/> Currently, there are limited images in ```.\data\samples```. If you want to test more images, can put them into samples folder

- Run simple tests
<br/> Please refer to Inference section in [README.md](https://github.com/ultralytics/yolov3)
```
python detect.py --cfg cfg/yolov3.cfg --weights weights/yolov3.weights
```

### 4. Moving direction determination (4.7 ~ 4.10)
#### Output .txt files for bounding box and label
- Line 19 of ```detect.py``` ```save_txt = True```. This will save .txt files in ```Output``` folder

#### Understand .txt file structure
- Each line contains 6 numbers. The first 4 numbers are bounding box coordinates. The 5th number is the category of the object. And the last number is confidence of the category
- ```.\data\coco.names``` specifies possible categories. The (5th number + 1) line is the corresponding type.

#### Focus on person type objects
For simplicity and purpose of the app, we only focus on person type objects
- ```detect.py```line 80 ```if int(cls) == 0:``` helps us to only mark person bounding box in output images.

#### Choose main object
In real conditions, there may be multiple people in front of the user, we need to compare bounding boxes size to determine which person is closer to user and take it as the main object.

#### Determine main object moving direction

### Transform detection and direction to voice (4.11 ~ 4.12)
Google text-to-voice API
https://towardsdatascience.com/object-detection-with-voice-feedback-yolo-v3-gtts-6ec732dca91
 
### Result (4.12 ~ 4.13)
 
### Paper writing (4.16 ~ 4.17)
overleaf online latex using AAAI author toolkit
 
### Detailed implementation


### Bouding Box
Each bounding box consists of 5 predictions: x, y, w, h, and confidence. The (x, y) coordinates represent the center of the box relative to the bounds of the grid cell. The width and height are predicted relative to the whole image.  Finally the confidence prediction represents the IOU between the predicted box and any ground truth box.

### Work Allocation
Assignment|People|
---|---|
Research on other papers & Run rough experiments & Compare its disadvantages over YOLOv3| Wang Tengda|
YOLOv3 detailed structure & techincal details | Tian Xueyan|
Bounding box comparison & Output video with voice | |
