# Human Activity Recognition using CNN in Keras for SensorTile (STMicroelectronics)
This repository contains the code for a small project. The aim of this project is to create a simple Convolutional Neural Network (CNN) based Human Activity Recognition (HAR) system for the SensorTile that is made by STMicroelectronics and it is a tiny, square-shaped IoT module that packs powerful processing capabilities leveraging an 80 MHz STM32L476JGY microcontroller and Bluetooth low energy connectivity based on BlueNRG-MS network processor as well as a wide spectrum of motion and environmental MEMS sensors, including a digital microphone..  
This system uses the sensor data from a 3D accelerometer for `x`, `y` and `z` axis and recognize the activity of the user e.g. `Walking`, going `Upstairs` and `Downstairs`.

### Files
The project is made of following files:
* `HAR.py`, Python script file containing the Keras implementation of the CNN based Human Activity Recognition (HAR) model;
* `output.txt`, Text file containing the dataset used in this experiment;
* `model.h5`, A pretrained model, trained on the training data;
* `evaluate_model.py`, Python script file containing the evaluation script. This script evaluates the performance of the pretrained netowrk on the provided testData;
* `testData.npy`, Python data file containing the testing data used for the evaluation of the available pretrained model;
* `groundTruth.npy`, Python data file containing the ground truth values for the corresponding outputs for for the test data;
* `README.md`.


### Tools Required
The code in this project is created using Python 3.\*. 
Following libraries are required to run the code provided in this repository:
* `Keras 2.*`
* `Numpy`
* `Matplotlib`
* `Pandas`
* `Sklearn`  
The accelerometer used for data acquisition is that of the [`STEVAL-STLKT01V1`](https://www.st.com/en/evaluation-tools/steval-stlkt01v1.html) that is is a comprehensive development kit designed to support and expand the capabilities of the SensorTile and comes with a set of cradle boards enabling hardware scalability.  
Furhtermore, they are need STMicroelectronics software's such as:
* [STM32CubeMX] (https://www.st.com/content/st_com/en/products/development-tools/software-development-tools/stm32-software-development-tools/stm32-configurators-and-code-generators/stm32cubemx.html);
* [X-CUBE-AI](https://www.st.com/en/embedded-software/x-cube-ai.html), expansion for STM32CubeMX.


### Dataset
In these experiments we used a dataset built collecting data of accelerometer using the STEVAL-STLKT01V1 development kit. These activities include:
* Downstairs;
* Upstairs;
* Walking.


### Training and Evaluation
A simple CNN based neural network is created using the topology in `HAR.py`. The dataset is splitted into two subgroups, `trainData` and `testData` with the ratio of `80` and `20`% respectively. The training data is further split into training and validation data with the same distribution.  
The HAR model created in `HAR.py` is then trained on the training data and validated on the validataion data. To evaluate the performance of this network, we write a script "evaluate_model.py". This script uses the `20%` of random samples in the dataset and tests the pretrained CNN model `model.h5`. Furhtermore, this script reports the percentage of the wrong predictions as error and creates a confusion matrix. 


### 