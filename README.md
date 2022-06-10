# Local-Control-Prediction

#### Team
[Anish Mukherjee](https://github.com/anmuai), [Young Zeng](github.com/youngzyx)

## Background
We were working on this project during our internship at University of California, San Francisco. The main task for this project is to predict the local control from three different types of data: image data, clinical data, and radiomics data. <br />

`Local control` After stereotactic radiosurgery such as gamma knife, if certain brain metastasis does not locally recur, then that would be local control. Otherwise that would be local failure. 

## Dataset
`Image data` 8461 3D MRI images with brain tumors and their masks. <br />
`Clinical data` 8407 tableau dataset with clinical features. <br />
`Radiomics data` 8407 tableau dataset with radiomics features. <br />

## Methodology
Modelling with three differet types of data respectively, then we model with the combination of clinical data and other types of data.

### Image Models
We tried different architectures of Convolutional Neural Network model such as UNet, ResNet 50. 
| Architecture|Best Accuracy|Best Area under ROC|
|:-----------|:------------:|:--------:|
|[UNet+Linear](UNet_Linear.ipynb)|0.9125|0.5992|
|[Half_UNet+Linear](Half_UNet_Linear_balancing.ipynb)|0.5073|0.5568|

### Models for tableau data
Since both clinical and radiomics data are tableau data. It would be easier for us to model them together. We used gradient boosting model from scikit learn, xgboost, and random forest models.

