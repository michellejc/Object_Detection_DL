# Object Detection: Raccoons
An exploration of basic Deep Learning classification and object detection techniques. This repository is a basic guide to getting started with object detection, and computer vision more generally. A basic knowledge of ML concepts, Python, and Pytorch are assumed, but the intention is for this repository to be easy to follow for anyone who is interested!

## Outline
1. Introduction <br>
  1.1 Summary and Goals <br>
  1.2 Datasets <br>
2. Modeling <br>
    2.1 Basic Object Detection <br>
  2.2 Data Augmentations <br>
  2.3 Batch Normalization <br>
3. Conclusion and Next Steps <br>

## 1. Introduction
### 1.1 Summary and Goals
In the following readme and accompanying notebooks we explore the basics of object detection. Our main goal is to provide an example for getting started in Object Detection, and to explore effective ways to increase model performance. To achieve this goal we found a simple dataset on Kaggle (see datasets below) and created a simple CNN model. From there we found the model was not performing well, so we tried two simple methods to improve it. First, we tried data augmentation with the Albumentations library and second we tried batch normalization. Then, we attempted to explore the relationship between loss functions and model performance through comparing MSE with IoU (more to come on that later). Finally, we looked into creating a multi-task model that could both classify an image and then identifying a bounding box.  Unfortunately, none of these technique worked perfectly, and perhaps we are coming away from this study with more questions than answers (welcome to DL).  

### 1.2 Datasets
1. The main dataset is from kaggle and can be found [here](https://www.kaggle.com/andrewmvd/animal-faces). This dataset includes 148 images of raccoons and a csv file with coordinates for the upper left and lower right corners of bounding boxes identifying where each raccoon is (see example below).

![alt text](https://github.com/michellejc/Object_Detection_DL/blob/main/OD_example.png)

2. The second dataset we chose is also from kaggle and can be found [here](https://www.kaggle.com/andrewmvd/animal-faces). This dataset includes 16,130 images of cats dogs and wildlife. We selected this dataset so we could explore adding another dimensions (classification of raccoon or not raccoon) to our dataset. This second dataset does not include bounding boxes, which for our purposes is absolutely fine. More on model details will be explored in the next section.

### 2 Modeling
### 2.1 Basic Object Detection

For this exploration we choose to experiment with a basic **Convolutional Neural Network (CNN)**. Our model has four convolutional layers with pooling between. We also use relu as our activation function and two linear layers at the end. Our final linear layer outputs a tensor with 4 predictions representing our bounding box coordinates.

As you can see in part one of the modeling notebook the basic dataset and simple CNN does not seem to train correctly. Neither the train loss or validation loss move. This could be cause by a number of factors including exploding/diminishing gradients. In the following sections we attempt two techniques **Data Augmentation** and **Batch Normalization** to try and help the basic CNN train better.

### 2.2 Data Augmentations

With small image datasets like ours, image transformations can be used to create synthetic data to increase your sample size and thus the variety of images the model sees. [Albumentations](https://albumentations.ai/) is a Python library that supports a wide variety of image augmentation which can perform simultaneous augmentation of multiple targets, including bounding boxes and keypoints. The transformation pipeline used in this project includes random crop, vertical and horizontal flip, rotation, and random brightness contrast.

![Image Augmentation](https://github.com/michellejc/Object_Detection_DL/blob/main/Image_Augmentation.png)

### 2.3 Batch Normalization

When we noticed that the basic has difficulty learning the bounding boxes, we decided to try **batch normalization**. Batch Normalization is a common normalization technique used to prevent overfitting/learning unnecessary or incorrect patterns in the data. One important thing to keep in mind when using batch normalization with images is to use the **BatchNorm2d** function - this will handle image inputs that BatchNorm1d cannot handle.

### 2.4 Loss Function Comparison (MSE and IoU)

We also wanted to explore the relationship between loss functions and model performance here. We believe that comparing the use of MSE vs. IoU loss may produce interesting results because the two loss functions may cause the model to highlight or learn different patterns. Unfortunately, for some reason we cannot get the function to produce a loss other than zero. In later iterations of this repository we will correct this function and compare how the model trains when using MSE vs IoU as a loss metric.

### 2.5 Multi-Task Model

## 3. Conclusion and Next Steps
