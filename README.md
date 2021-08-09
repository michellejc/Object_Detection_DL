# Object_Detection_DL
An exploration of basic Deep Learning classification and object detection techniques. This repository is a basic guide to getting started with object detection, and perhaps computer vision more generally. A basic knowledge of ML concepts, Python, and Pytorch are assumed, but hopefully will be easy to follow for anyone who is interested! 

## Outline 
### 1. Introduction
#### 1.1 Datasets
1. The main dataset we chose for is from kaggle and can be found [here](https://www.kaggle.com/andrewmvd/animal-faces). This dataset includes 200 images of raccoons and a csv file with coordinates for the upper left and lower right corners of bounding boxes identifying where each raccoon is (see example below). 

![alt text](https://github.com/michellejc/Object_Detection_DL/blob/main/OD_example.png)

2. The second datase we chose is also from kaggle and can be found [here](https://www.kaggle.com/andrewmvd/animal-faces). This dataset includes 16,130 images of cats dogs and wildlife. We selected this dataset so we could explore adding another dimesion (classification of raccoon or not raccoon) to our dataset. This second dataset does not include bounding boxes, which for our purposes is absolutely fine. More on model details will be explored in the next section. 

#### 1.2 Basic Model
Our modeling exploration taskes place over three main steps:
  A. First, we create a basic model that performs one task - object detection. For this model we implement a basic CNN structure and using MSE as our loss function (more on metrics to come in section 3.2). The details of the model can be found in this notebook **INSERT LINK TO NOTEBOOK**.
  B. Se
  C.
### 2. Data Augmentation with Albumentations Library 
One challenge we faced 
### 3. Modeling 
#### 3.1 Basic Object Detection
#### 3.2 A Discussion of Metrics 
#### 3.3 Classification and Object Detection
#### 4. Conclusion and Next Steps 

## 1. Introduction
In order 
