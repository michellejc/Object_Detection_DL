# Object_Detection_DL
An exploration of basic Deep Learning classification and object detection techniques. This repository is a basic guide to getting started with object detection, and computer vision more generally. A basic knowledge of ML concepts, Python, and Pytorch are assumed, but the intention is for this repository to be easy to follow for anyone who is interested!

## Outline
1. Introduction
  1.1 Summary and Goals
  1.2 Datasets
2. Modeling
  2.1 Basic Object Detection
  2.2 Data Augmentations
  2.3 Batch Normalization
3. Conclusion and Next Steps

## 1. Introduction
### 1.1 Summary and Goals
In the following readme and accompanying notebooks we explore the basics of object detection. Our main goal is to provide an example for getting started in Object Detection, and to explore effective ways to increase model performance. To achieve this goal we found a simple dataset on Kaggle (see datasets below) and created a simple CNN model. From there we found the model was not performing well, so we tried two simple methods to improve it. First, we tried data augmentation with the Albumentations library and second we tried batch normalization. Then, we attemted to explore the relationship between loss functions and model performance through comparing MSE with IoU (more to come on that later). Finally, we looked into creating a multi-task model that could both classify an image and then idenfying a bounding box.  Unfortunately, none of these technique worked perfectly, and perhaps we are coming away from this study with more questions than answers (welcome to DL).  

### 1.2 Datasets
1. The main dataset we chose for is from kaggle and can be found [here](https://www.kaggle.com/andrewmvd/animal-faces). This dataset includes 200 images of raccoons and a csv file with coordinates for the upper left and lower right corners of bounding boxes identifying where each raccoon is (see example below).

![alt text](https://github.com/michellejc/Object_Detection_DL/blob/main/OD_example.png)

2. The second dataset we chose is also from kaggle and can be found [here](https://www.kaggle.com/andrewmvd/animal-faces). This dataset includes 16,130 images of cats dogs and wildlife. We selected this dataset so we could explore adding another dimensions (classification of raccoon or not raccoon) to our dataset. This second dataset does not include bounding boxes, which for our purposes is absolutely fine. More on model details will be explored in the next section.

### 2 Modeling
### 2.1 Basic Object Detection

### 2.2 Data Augmentations

### 2.3 Batch Normalization

### 2.4 Loss Function Comparison

### 2.5 Multi-Task Model

## 3. Conclusion and Next Steps
