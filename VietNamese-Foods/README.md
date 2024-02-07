# Vietnamese Foods Classification

## Overview

Vietnamese Foods Classification is a project aimed at accurately classifying traditional Vietnamese dishes. With the rich culinary heritage of Vietnam, this project focuses on automatically identify and categorize various traditional dishes based on their images or videos.

### Table of Contents

- [Prerequisites](#prerequisites)
- [Dataset Preparation](#dataset-preparation)
- [Model Architecture](#model-architecture)
- [Training and Evaluation](#training-and-evaluation)
- [Results](#results)

## Prerequisites

Before starting the project, you should install necessary dependencies in your device, but I recommend upload the file on <a href="https://colab.research.google.com/"><img src="https://colab.research.google.com/assets/colab-badge.svg"></a> because of several conveniences.

## Dataset Preparation

My dataset usage is downloaded from <a href="https://www.kaggle.com/datasets/quandang/vietnamese-foods"><img src="https://kaggle.com/static/images/open-in-kaggle.svg"></a>. This dataset was introduced in paper <a href="https://ieeexplore.ieee.org/abstract/document/9530774">30VNFoods: A Dataset for Vietnamese Foods Recognition</a> where contains 30 VietNamese cuisines with 25136 images.

The structure of dataset should be:

```
Images
|
--- train
|   |
|   --- Banh Beo
|   |   |
|   |   --- 1.jpg
|   |   --- 2.jpg
|   |   --- ...
|   --- Banh Mi
|   |   --- 1.jpg
|   |   --- 2.jpg
|   |   --- ...
|   ...
--- val (identical to train)
|
--- test (identical to train)
```

## Model Architecture

I leverage the pretrained model YOLOv8 (weights: [yolov8x-cls.pt](https://docs.ultralytics.com/tasks/classify/#models)), which is trained on ImageNet dataset.

## Training and Evaluation

In my experiment, I will use some `augmentation data techniques`, including rotation, translation, etc. If you want to modify the configurations, please visit [Ultralytics Docs](https://docs.ultralytics.com/usage/cfg/#train) for more details.

After training, the results will be stored in `runs/classify/train`, which includes 2 weights files, `best.pt` and `last.pt`, respectively. In addition, some evaluation metrics such as confusion matrix, confusion_matrix_normalized and visualization of training data are stored in the same path.

## Results

![Alt text](image.png)
