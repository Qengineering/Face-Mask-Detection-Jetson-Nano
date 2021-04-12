# Face-Mask-Detection-Jetson-Nano
![output image]( https://qengineering.eu/images/FamilyOut.jpg )

## A fast face mask recognition running at 44-5 FPS on a Jetson Nano.
[![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)<br/><br/>
This is a fast C++ implementation of two deep learning models found in the public domain. <br/><br/>
The first is face detector of Linzaer running on a ncnn framework.<br/> 
https://github.com/Linzaer/Ultra-Light-Fast-Generic-Face-Detector-1MB. <br/><br/>
The second is the Paddle Lite mask detection which classifies the found faces.<br/> 
https://github.com/PaddlePaddle/Paddle-Lite/tree/develop/lite/demo/cxx/mask_detection. <br/><br/>
The frame rate depends on the number of detected faces and can be calculated as follows: <br/>
FPS = 1.0/(0.022 + 0.008 x #Faces) when overclocked to 2014 MHz. <br/><br/>
Paper: https://arxiv.org/abs/1905.00641.pdf <br/>
Size: 320x320 <br/><br/>
Special made for a Jetson Nano see [Q-engineering deep learning examples](https://qengineering.eu/deep-learning-examples-on-raspberry-32-64-os.html) <br/>
### New version 2.0.
A new and superior version with only __TensorFlow Lite__ for a Jetson Nano see [GitHub](https://github.com/Qengineering/TensorFlow_Lite_Face_Mask_Jetson-Nano) <br/>
## Dependencies.
### April 4 2021: Adapted for ncnn version 20210322
To run the application, you have to:
- The Paddle Lite framework installed. [Install Paddle](https://qengineering.eu/install-paddle-on-jetson-nano.html) <br/>
- The Tencent ncnn framework installed. [Install ncnn](https://qengineering.eu/install-ncnn-on-jetson-nano.html) <br/>
- Code::Blocks installed. (```$ sudo apt-get install codeblocks```)
## Running the app.
To extract and run the network in Code::Blocks <br/>
$ mkdir *MyDir* <br/>
$ cd *MyDir* <br/>
$ wget https://github.com/Qengineering/Face-Mask-Detection-Jetson-Nano/archive/refs/heads/master.zip <br/>
$ unzip -j master.zip <br/>
Remove master.zip and README.md as they are no longer needed. <br/> 
$ rm master.zip <br/>
$ rm README.md <br/> <br/>
Your *MyDir* folder must now look like this: <br/> 
Face_1.jpg <br/>
Face_2.jpg <br/>
Face_3.jpg <br/>
Face_Mask_Video.mp4 <br/>
mask_detector_opt2.nb <br/>
MaskUltra.cpb <br/>
mask_ultra.cpp <br/>
UltraFace.cpp <br/>
UltraFace.hpp <br/>
RFB-320.bin <br/>
RFB-320.param <br/>
slim_320.bin <br/>
slim_320.param <br/>
### Notes. 
The directories in the Code::Blocks project file will probably need to be adapted to the naming convention you are using. <br/>
The camera input used is a simple OpenCV webcam. The GStreamer is not used in this example for symplicity reasons.<br/><br/>
The RFB-320 model recognizes slightly more faces than slim_320 at the expense of a little bit of speed. It is up to you.<br/>
Note that the compilation of the Paddle Lite framework in your application may take a while. <br/> <br/>
See the Raspberry Pi video at https://youtu.be/LDPXgJv3wAk
