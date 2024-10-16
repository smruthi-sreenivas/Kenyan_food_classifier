This project is a multi-class classification project, where you have to classify each image into any one of the 13 Kenyan food classes.
The evaluation metric for this competition is the Accuracy score. It is the ratio of the number of correct predictions to the total number of input samples. In classification, the Accuracy score is given by:

Acc=Numberofcorrectpredictions/Totalnumberofpredictions

**Dataset Description**
The dataset consists of 8,174 images in 13 Kenyan food type classes. Sample images of the KenyanFood13 dataset and the number of images in each of the classes are shown below:

![image](https://github.com/user-attachments/assets/99b2e9e2-0533-44c1-856a-c1511272068b)

This Kenyan food classification project is an imbalanced dataset interms of number of data samples per class.
As most pretrained models are trained on IMAGENT datasets, when our dataset is varied a lot means just doing transfer learning with changing the number of classes in the last classification layer might not always help. Doing Transfer Learning, the maximum accuracy got was 70% using ConvNext_large.
In such cases we might need to finetune by unfreezing last few backbone or feature extraction layers so that the model learns
effectively some features along with its earlier layers freezed. This can make the model adept to our dataset and greatly help.
For this classification tasks I have used FocalLoss to calculate loss as there is a large class imbalance. It focuses on learning hard examples, thereby enhancing generalization to minority classes.
I tried ensemble learning. I trained ConvNext_large and EfficientNet sequentially and weighted sum of all model predictions are taken as the final prediction. I was able to get an improved accuracy of 76.3%.
