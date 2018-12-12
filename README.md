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

(3). Go to your directory where you extarcted all the files and open a cmd. Then for isntalling cython type "conda install -c anaconda cython" and then type "python setup.py build_ext --inplace"

Now we can start training :)

## Training the model

(1). 
