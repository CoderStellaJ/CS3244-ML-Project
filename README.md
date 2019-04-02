# CS3244-ML-Project
Blind people voice guide app
<br/>Created by National University of Singapore CS3244 Machine Learning Group 26. All of us are equally contributed.
<br/>[Jin Shuyuan](https://github.com/CoderStellaJ), [Mou Ziyang](https://github.com/mouziyanglovestudy), [Tian Xin](https://github.com/tianxin9628), [Tian Xueyan](https://github.com/xueyantian), [Wang Tengda](https://github.com/JacobWangTengda), [Zhao Tianze](https://github.com/tankztz)

### App features
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
  
  
### Research on dataset and neural network (4.1 ~ 4.2)
Neural Network |NN Link| Description | Paper
--- | --- | ---| --- |
YOLOv3 |https://pjreddie.com/darknet/yolo/ |Developed from YOLO |  |
YOLO | | YOLO is a state-of-the-art, real-time object detection system. It has Pretrained Convolutional Weights which is tarined on Imagenet.|https://pjreddie.com/media/files/papers/yolo.pdf |
R-CNN  | | | | https://arxiv.org/pdf/1311.2524.pdf |

![github-small](https://github.com/CoderStellaJ/CS3244-ML-Project/blob/master/Baselines.PNG)

Dataset| Link| Description |
---|---|---|
ImageNet | http://www.image-net.org/ |  |
COCO dataset|http://cocodataset.org/#home ||
Pascal VOC challenge|http://host.robots.ox.ac.uk/pascal/VOC/index.html| |
### NN implementations (4.3 ~ 4.6)
 
### Moving direction determination (4.7 ~ 4.10)
compare bounding box size in sequential images
 
### Result (4.11 ~ 4.13)
 
### Paper writing (4.16 ~ 4.17)
overleaf online latex using AAAI author toolkit
 
### Detailed implementation

