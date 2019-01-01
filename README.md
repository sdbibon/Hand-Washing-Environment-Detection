# Hand-Washing-Environment-Detection

## Dependencies:

Python 3.6, tensorflow 1.0 with gpu, Anaconda, numpy, opencv 3 

## Installation instruction:

Python : https://www.python.org/downloads/

Tensorflow-gpu : https://www.pugetsystems.com/labs/hpc/The-Best-Way-to-Install-TensorFlow-with-GPU-Support-on-Windows-10-Without-Installing-CUDA-1187/
Tutorial: https://www.youtube.com/watch?v=Ebo8BklTtmc

Anaconda: https://www.anaconda.com/download/#windows from here download anaconda for python 3.6 and don't forget the set environment variables path after installation.

numpy: after installing python, tensorflow and anaconda open a command prompt using cmd or anaconda prompt, then type "conda install -c anaconda numpy" or "python -m pip install numpy" or "pip install numpy"

opencv3 : open a anaconda prompt or command prompt then type "conda install -c conda-forge opencv" or follow this tutorial https://www.youtube.com/watch?v=9hb0gYCv3YI 

All your installation done :)

## Instructions before training the model

(1). Download the github repository https://github.com/sdbibon/Hand-Washing-Environment-Detection.git as zip file and extract to anywhere you like.

(2). Go the link https://drive.google.com/file/d/1lQJgadkiralHlTOIM-WlBuXROLQryQyU/view?usp=sharing and download the zip file. After that extract the bin, sample_img and trained_data in the folder where you extracted the github repository.

It will look like this
![p](https://user-images.githubusercontent.com/16569879/49892716-ddd85000-fe06-11e8-848c-6d27b5bdbda8.JPG)

(3). Go to your directory where you extarcted all the files and open a cmd. Then for installing cython type **"conda install -c anaconda cython"** and then type **"python setup.py build_ext --inplace"**

Now we have our cfg file, yolov2 and tiny yolo weights in bin folder and for training images and annotations(xmls). We can now start training :)

## Training the model

(1). Training in tiny yolo

Go to the directory where you extracted the github repository and open a command prompt or anaconda prompt.If you have tensorflow-gpu and want in train in gpu using tiny-yolo-voc weights then type

**"python flow --model cfg/tiny-yolo-voc-5c.cfg --load bin/tiny-yolo-voc.weights --train --annotation trained_data/Annotations --dataset trained_data/Images --gpu 0.8"**

If you want to train on cpu then type

**"python flow --model cfg/tiny-yolo-voc-5c.cfg --load bin/tiny-yolo-voc.weights --train --annotation trained_data/Annotations --dataset trained_data/Images"**

(2). Training in YOLOv2

Go to the directory where you extracted the github repository and open a command prompt or anaconda prompt.If you have tensorflow-gpu and want in train in gpu using tiny-yolo-voc weights then type

**"python flow --model cfg/yolov2-voc-5c.cfg --load bin/yolov2-voc.weights --train --annotation trained_data/Annotations --dataset trained_data/Images --gpu 0.8"**

If you want to train on cpu then type

**"python flow --model cfg/yolov2-voc-5c.cfg --load bin/yolov2-voc.weights --train --annotation trained_data/Annotations --dataset trained_data/Images"**

If you want to train in tiny yolov2 then change the cfg instruction as **yolov2-tiny-voc-5c.cfg** and for weights **yolov2-tiny-voc.weights**

(3). If the training starts sucessfully then you will see this

![lll](https://user-images.githubusercontent.com/16569879/49894379-111cde00-fe0b-11e8-86b4-3bf760109e21.JPG)

(4). Train until the average comes less than 1 or for better 0.5. After training your model you will see in the ckpt folder the new weights are generating.

Now we can test our model. :)

## Testing our model

(1). For testing in videos, place a video in the same extracted directory, name it as video1.mp4. Go to the directory where you extracted the github repository and open a command prompt or anaconda prompt. 

Type the instructions:
**"python flow --model cfg/tiny-yolo-voc-5c.cfg --load -1 --demo video1.mp4 --gpu 0.8"**
or
**"python flow --model cfg/yolov2-voc-5c.cfg --load -1 --demo video1.mp4 --gpu 0.8"**

For CPU use
**"python flow --model cfg/tiny-yolo-voc-5c.cfg --load -1 --demo video1.mp4"**
or
**"python flow --model cfg/yolov2-voc-5c.cfg --load -1 --demo video1.mp4"**


New video file named as video.mp4 will be created. There you can see the test results of detected Hands, Faucets, Sinks , Soap Dispensers or Stethoscopes

## Final test result video

(1). If the train is sucsessful then you can test by your own.
For checking the test check the following video or go the folder test result videos
[TinyYolo.zip](https://github.com/sdbibon/Hand-Washing-Environment-Detection/files/2673314/TinyYolo.zip)

Some screenshot are givden below:

![fig16](https://user-images.githubusercontent.com/16569879/50575773-aa636280-0dc1-11e9-80cd-1aa4599044aa.jpg)


