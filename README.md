# colon-cancer-deep-learning
Deep learning-based classification of colon cancer histopathology images using ResNet50 transfer learning.
# Deep Learning-Based Metastasis Prediction from Colon Cancer Histopathology Images

Project Overview

This project explores the application of deep learning for automated classification of colon cancer histopathology images. The objective was to develop a ResNet50-based image classification model capable of distinguishing **Colon Adenocarcinoma** from **Colon Benign Tissue** using histopathological images.

The project was developed as an academic M.Sc. thesis project using Python and TensorFlow/Keras in Google Colab.

## Domain

* Bioinformatics
* Deep Learning
* Medical Image Analysis
* Cancer Research
* Computer Vision

## Dataset

The histopathology images were obtained from a publicly available dataset hosted on Kaggle. The original dataset contained approximately 25,000 images covering lung and colon cancer tissues.

For this project, the colon cancer images were separated from the dataset, resulting in approximately **10,000 colon histopathology images** belonging to two classes:

* Colon Adenocarcinoma (`colon_aca`)
* Colon Benign Tissue (`colon_n`)

The dataset is not included in this repository.

## Project Workflow

The project followed the following workflow:

1. Dataset collection
2. Selection of colon cancer images
3. Image preprocessing
4. Image resizing and normalization
5. Dataset organization and labeling
6. Stratified dataset splitting
7. Data augmentation
8. ResNet50 transfer learning and fine-tuning
9. Model training
10. Model evaluation
11. Prediction and performance analysis

## Data Preprocessing

The histopathology images were processed using Python and OpenCV.

The preprocessing pipeline included:

* Reading images using OpenCV
* Resizing images to **224 × 224 pixels**
* Normalizing pixel values to the **0–1 range**
* Organizing images according to their respective classes

The processed images were then used for deep learning model development.

## Dataset Splitting

The dataset was divided using stratified random sampling to maintain the class distribution:

| Dataset    | Percentage |
| ---------- | ---------: |
| Training   |        80% |
| Validation |        10% |
| Testing    |        10% |

A fixed random state of 123 was used during dataset splitting.

## Data Augmentation

Data augmentation was applied to the training images to improve model generalization and reduce overfitting.

The augmentation techniques included:

* Rotation
* Width shifting
* Height shifting
* Shearing
* Zooming
* Horizontal flipping

## Deep Learning Model

A **ResNet50** convolutional neural network pretrained on ImageNet was used as the base model.

The model architecture consisted of:

* ResNet50 pretrained base
* Global Average Pooling
* Dense layer with 1024 neurons and ReLU activation
* Dropout layer with a rate of 0.5
* Final Dense layer with 2 output classes using Softmax activation

Fine-tuning was performed by freezing the first 100 layers of the ResNet50 base model while allowing the remaining layers to train.

Class weights were also calculated to help balance model learning.

## Training Configuration

| Parameter          | Value                     |
| ------------------ | ------------------------- |
| Model              | ResNet50                  |
| Pretrained Weights | ImageNet                  |
| Input Size         | 224 × 224 × 3             |
| Batch Size         | 64                        |
| Optimizer          | Adam                      |
| Learning Rate      | 0.00001                   |
| Loss Function      | Categorical Cross-Entropy |
| Epochs             | 20                        |
| Output Classes     | 2                         |

## Evaluation

The trained model was evaluated using:

* Training accuracy and loss
* Validation accuracy and loss
* Test accuracy and loss
* Confusion matrix
* Classification report
* Precision
* Recall
* F1-score

The project also included prediction of individual sample histopathology images using the trained model.

## Tools and Technologies

### Programming Language

* Python

### Deep Learning

* TensorFlow
* Keras
* ResNet50

### Image Processing

* OpenCV
* PIL

### Data Analysis

* NumPy
* Pandas
* Scikit-learn

### Data Visualization

* Matplotlib
* Seaborn

### Development Platform

* Google Colab
* NVIDIA T4 GPU

## Repository Contents

```text
colon-cancer-histopathology-deep-learning/
│
├── README.md
├── requirements.txt
│
├── notebooks/
│   └── Colon_cancer_Histopathology_ResNet50.ipynb
│
└── results/

 Key Learning Outcomes

This project provided practical experience in:

* Medical image classification
* Deep learning and convolutional neural networks
* Transfer learning
* ResNet50 fine-tuning
* Image preprocessing
* Data augmentation
* Dataset preparation and stratified splitting
* Model evaluation
* Python programming
* TensorFlow/Keras
* Bioinformatics and computational cancer research

Academic Project

Project Title: Deep Learning-Based Metastasis Prediction from Colon Cancer Histopathology Images

Project Type: M.Sc. Academic Thesis

Author: Anam Sayyed
