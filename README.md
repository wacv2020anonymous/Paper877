# [On the Texture Bias for Few-Shot CNN Segmentation](https://arxiv.org/pdf/2003.04052.pdf)

This repository contains the code for the WACV submission 877
## Prerequisties and Run
This code has been implemented in python language using Keras libarary with tensorflow backend and tested in ubuntu OS, though should be compatible with related environment. following Environement and Library needed to run the code:

- Python 3
- Keras version 2.2.0
- tensorflow backend version 1.13.1


## Run Demo
The implementation code is availabel in Source Code folder.</br>
1- Download the FSS1000 dataset from [this](https://drive.google.com/open?id=16TgqOeI_0P41Eh3jWQlxlRXG9KIqtMgI) link and extract the dataset.</br>
2- Run `Train_DOGLSTM.py` for training Scale Space Encoder model using k-shot episodic training. The model will be train for 50 epochs and for each epoch it will itterate 1000 episodes to train the model. The model will saves validation performance history and the best weights for the valiation set. It also will report the MIOU performance on the test set. The model by default will use VGG backbone with combining Block 3,4 and 5 but other combination can be call in creatign the model. It is also possible to use any backbone like Resnet, Inception and etc.... </br>
3- Run `Train_weak.py` for training Scale Space Encoder model using k-shot episodic training and evaluatign on the weak annotation test set. This code will use weaklly annotated bouning box as a label for the support set on test time.

Notice: `parser_utils.py` can be used for hyper parameter setting and defining data set address, k-shot and n-way.

## Quick Overview
![Diagram of the proposed method](https://github.com/rezazad68/fewshot-segmentation/blob/master/githubimages/Figure1.png)

### Structure of the Proposed Scale Space encoder for reducing texture bias effect
![Diagram of the SSR](https://github.com/rezazad68/fewshot-segmentation/blob/master/githubimages/Figure2.png)

### Visual representation of 21 classes from 1000-class dataset with their masks and generated bounding box [Download link](https://github.com/rezazad68/fewshot-segmentation/raw/master/FSS-1000%20Bounding%20Box%20Annotation.zip)
![Bounding Box annotation for FSS-1000](https://github.com/rezazad68/fewshot-segmentation/blob/master/githubimages/Weak%20Annotation%20samples%20for%20FSS1000.jpg)



#### Visual Segmentation result on Pascal 5i
Sample of 1-shot segmentation result on the Pascal 5i dataset 
![Pascal 5i Result 1](https://github.com/rezazad68/fewshot-segmentation/blob/master/githubimages/VOC_segmentation%20result%20.jpg)

### Extra results
#### Visual representation of proposed method performing segmentation on 1000 class dataset.
![FSS1000 Result 2](https://github.com/rezazad68/fewshot-segmentation/blob/master/githubimages/FSS1000%20result%202.jpg)
#### Visual demonstration of the proposed method limitation in segmenting the object of interest
![FSS1000 Result 3](https://github.com/rezazad68/fewshot-segmentation/blob/master/githubimages/FSS1000%20bad%20segmentation.jpg)
#### Visual representation of proposed method performing segmentation on 1000 class dataset with weak annotation (bounding box)
![FSS1000 Result 4](https://github.com/rezazad68/fewshot-segmentation/blob/master/githubimages/Weak%20annotation%20result%201.jpg)
![FSS1000 Result 5](https://github.com/rezazad68/fewshot-segmentation/blob/master/githubimages/FSS1000%20Weak%20result%202.jpg)


