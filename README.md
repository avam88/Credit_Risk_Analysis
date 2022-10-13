# Peer to Peer Lending Credit Risk Analysis

## Using the fully library of machine learning models, we will run our lending dataset through each model to determine the model with the highest level of accuracy and sensitivity for predicting candidates who are at a high risk of defaulting on their loans. In our approach we will use undersampling, oversampling and the SMOTEENN approach (a combination of both oversampling minority data and undersampling majority data) and compare the resulting confusion matrices and classification report statistics as metrics for the models predictive performance.


## Results:
The following language and metrics are used to assess the quality of each machine learning model and its overall score for predicting outcomes.
- Precision is the measure of accuracy for true positives (how likely is a positive result actually true). Precision is measured using the following algorithm with values produced by the confusion matrix. 
  - Precision = True Positive/(True Positive + False Positive)
  - The closer the Precision value is to 1, the more precise the model

- Sensitivity is a measure of how many true positives a model identifies. 
  - Sensitivity = True Positive/(True Positive + False Negative)  
  - The closer the Sensitivity (or Recall) value is to 1 the more sensitive the model

- The F1 Score is a single summarizing statistics that takes into account precision and sentivity values, as they can often be at odds. The formula for generating the F1 score of a machine learning model is
  -  2(Precision * Sensitivity)/(Precision + Sensitivity)
  - The more balanced Sensitivity and Precision scores are the higher the F1 score, the more imbalanced, the lower the F1 score

- The confusion matrix (below) is the table and visual representation of predicted outcomes and actual outcomes used to produce our True/False Positives and True/False Negatives used in determing sensitivity and precision.
![Screen Shot 2022-10-12 at 5 48 22 PM](https://user-images.githubusercontent.com/107326987/195473717-046442d8-2d49-4e3d-8bfd-1ea829108f3d.png)

- The Classification Report includes the Precision, Recall (Sensitivity) and F1 scores for each of the dichotomous outcome metrics for the machine learning model.

Below are the scores for each of the machine learning models that use different variations of over and undersampling the minority or majority data.

### Naive Random Oversampling
- This model is not precise at all in predicting high risk loan candidates (0.01) but very precise in predicting low risk loan candidates. The metrics for sensitivity fall in line with precision metrics but with less divergent values. Ultimately the model is okay at accurately identifying high risk candidates, and slightly better at accurately identifying low risk loan candidates (0.61 and 0.69 respectively). The model is fairly performative for assessing and predicting low risk candidates but is ineffective for high risk candidates.

![random_oversample_cm](https://user-images.githubusercontent.com/107326987/195473185-d508640d-8a73-4b9d-a155-8c2582a705db.png)

![random_oversample_classification](https://user-images.githubusercontent.com/107326987/195473165-bd7ba697-b3a7-45e7-8322-33ffbf978777.png)

### SMOTE Oversampling
- We see similar metrics in the SMOTE Oversampling method as the Naive Random Oversampling, with slightly less performative measures with an overall F1 score of 0.79 (as compared to 0.81 for Naive Random Oversampling).

![smote_oversample_cm](https://user-images.githubusercontent.com/107326987/195473262-54c8982f-36d1-4876-b29c-315025339d57.png)

![smote_oversample_classification](https://user-images.githubusercontent.com/107326987/195473270-8a43bbea-4a93-46a9-a28f-1240ec3e9f34.png)

### Undersampling
- Undersampling in machine learning using the same dataset effectively decreases the credibility of the model compared to both SMOTE and Naive Randomg Oversampling. This model is not recommended for use.

![cluster_undersample_cm](https://user-images.githubusercontent.com/107326987/195473352-af63bc1d-4b4d-4cd9-a911-076eb23080cc.png)

![cluster_undersample_classification](https://user-images.githubusercontent.com/107326987/195473361-2771f0db-a230-4b76-8c8d-8ba75aa2d0f9.png)

### Combination (Over and Under) Sampling
- This model performs poorly, producing similar metrics to Undersampling the data.

![smoteenn_cm](https://user-images.githubusercontent.com/107326987/195473468-819d82a8-1470-44f6-a2fc-9924a6bf9f85.png)

![smoteenn_classification](https://user-images.githubusercontent.com/107326987/195473475-9cc5b2bd-ec17-4a67-bdf5-afdd34900d4e.png)

### Balanced Random Forest Classifier
- There is a marked improvement in this models performance outcomes compared to each previous model. Random Forest modeling is better at avoiding over-fitting and this is reflected in the performance metrics - here is the first model that performs well at both precision and sensitivity for predicting high risk loan candidates.

![brf_cm](https://user-images.githubusercontent.com/107326987/195473413-53ede6d5-3ad3-4c82-9ed2-4469e7f2a373.png)

![brf_classification](https://user-images.githubusercontent.com/107326987/195473424-129686a5-662f-4104-b161-5a41b49c8266.png)

### Easy Ensemble AdaBoost Classifier
- The most performative machine learning model - Adaptive Boosting allows the model to perform its data fitting several times, each time learning from its miss-classifications. This model provides the best precision and sensitivity scores for both low and high risk loand candidates.

![adaboost_cm](https://user-images.githubusercontent.com/107326987/195473511-84d70739-37dd-415d-9e15-15d40eaf8ea9.png)

![adaboost_classification](https://user-images.githubusercontent.com/107326987/195473519-211993af-6a85-47a4-b21c-202d30fe5e80.png)

## Summary Analysis: 
### We are looking for a model that has the highest sensitivity score (recall in the classification table) and also high precision for high risk candidates, which is paramount to achieving the same metrics for low risk candidates. We can see small variations in the overall performance across all models with the exception of the Easy Ensemble AdaBoost Classifier model. This is the most performative machine learning model, the recommendation is to use this model for predicting and assessing risk factors in loan candidates.

