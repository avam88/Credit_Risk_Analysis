# Peer to Peer Lending Credit Risk Analysis

## Using the fully library of machine learning models, we will run our lending dataset through each model to determine the model with the highest level of accuracy and sensitivity for predicting candidates who are at a high risk of defaulting on their loans. In our approach we will use undersampling, oversampling and SMOTEENN approach (a combination of both oversampling minority data and undersampling majority data) and compare the resulting confusion matrices and classification report statistics as metrics for the models success at predicting.


## Results:

Precision = TP/(TP + FP) : He wants to know how likely it is that he actually has cancer. Precision, also known as positive predictive value (PPV), is a measure of this. The closer to 1 the more precise
Sensitivity = TP/(TP + FN) : Sensitivity is a measure of how many people who actually have cancer were correctly diagnosed. the closer to 1 the more sensitive

F1 Score
The F1 score, also called the harmonic mean, can be characterized as a single summary statistic of precision and sensitivity. The formula for the F1 score is the following:


2(Precision * Sensitivity)/(Precision + Sensitivity)
 A useful way to think about the F1 score is that a pronounced imbalance between sensitivity and precision will yield a low F1 score.
![Screen Shot 2022-10-12 at 5 48 22 PM](https://user-images.githubusercontent.com/107326987/195473717-046442d8-2d49-4e3d-8bfd-1ea829108f3d.png)

classification report : precision, recall(=sensitivity), f1, support

### Naive Random Oversampling
-

![random_oversample_cm](https://user-images.githubusercontent.com/107326987/195473185-d508640d-8a73-4b9d-a155-8c2582a705db.png)

![random_oversample_classification](https://user-images.githubusercontent.com/107326987/195473165-bd7ba697-b3a7-45e7-8322-33ffbf978777.png)

### SMOTE Oversampling
- 

![smote_oversample_cm](https://user-images.githubusercontent.com/107326987/195473262-54c8982f-36d1-4876-b29c-315025339d57.png)

![smote_oversample_classification](https://user-images.githubusercontent.com/107326987/195473270-8a43bbea-4a93-46a9-a28f-1240ec3e9f34.png)

### Undersampling
-
![cluster_undersample_cm](https://user-images.githubusercontent.com/107326987/195473352-af63bc1d-4b4d-4cd9-a911-076eb23080cc.png)

![cluster_undersample_classification](https://user-images.githubusercontent.com/107326987/195473361-2771f0db-a230-4b76-8c8d-8ba75aa2d0f9.png)

### Combination (Over and Under) Sampling
-
![smoteenn_cm](https://user-images.githubusercontent.com/107326987/195473468-819d82a8-1470-44f6-a2fc-9924a6bf9f85.png)

![smoteenn_classification](https://user-images.githubusercontent.com/107326987/195473475-9cc5b2bd-ec17-4a67-bdf5-afdd34900d4e.png)

### Balanced Random Forest Classifier
-
![brf_cm](https://user-images.githubusercontent.com/107326987/195473413-53ede6d5-3ad3-4c82-9ed2-4469e7f2a373.png)

![brf_classification](https://user-images.githubusercontent.com/107326987/195473424-129686a5-662f-4104-b161-5a41b49c8266.png)

### Easy Ensemble AdaBoost Classifier
- 
![adaboost_cm](https://user-images.githubusercontent.com/107326987/195473511-84d70739-37dd-415d-9e15-15d40eaf8ea9.png)

![adaboost_classification](https://user-images.githubusercontent.com/107326987/195473519-211993af-6a85-47a4-b21c-202d30fe5e80.png)

## Summary Analysis: Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. If you do not recommend any of the models, justify your reasoning.
