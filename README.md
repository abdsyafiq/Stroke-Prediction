# Stroke-Prediction
This repository contains project EDA and create model machine learning, with data obtained from [Kaggle](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset).

# Background
According to the World Health Organization (WHO) stroke is the 2nd leading cause of death globally, responsible for approximately 11% of total deaths. This dataset is used to predict whether a patient is likely to get stroke based on the input parameters like gender, age, various diseases, and smoking status. Each row in the data provides relavant information about the patient.

# ML Modeling
The data used has a fairly extreme imbalance, namely only about 5% have a stroke. Therefore, handling class imbalance so that the data is more stable. In addition to doing normalization and standardization for numerical features.

The selection of the model is based on the consideration of the highest Recall score, to suppress False Negatives so that they are not large. It would be very dangerous if it was said to be a stroke, but predictably it was not said to be a stroke.

Before modelling, the data is split into train and test dataset (80% train and 20% test). The data then trained using 9 different algorithm:

Model | Accuracy | Precision | Recall | AUC |
--- | --- | --- | --- |--- |
KNN | 0.89 | 0.77 | 0.92 | 0.95 |
RandomForest | 0.92 | 0.87 | 0.88 | 0.97 |
Catboost | 0.94 | 0.94 | 0.85 | 0.98 |
DecisionTree | 0.87 | 0.80 | 0.81 | 0.86 |
XGBoost | 0.84 | 0.75 | 0.76 | 0.92 |
GradientBoosting | 0.86 | 0.79 | 0.75 | 0.93 |
SVM | 0.82 | 0.73 | 0.72 | 0.90 |
AdaBoost | 0.81 | 0.70 | 0.68 | 0.88 |
LogisticRegression | 0.78 | 0.67 | 0.62 | 0.86 |

# Model Evaluation
k-Nearest Neighbors gives highest recall score. This model then tuned with hyperparameter tuning.

KNN | Accuracy | Precision | Recall | AUC |
--- | --- | --- | --- |--- |
Before | 0.89 | 0.77 | 0.92 | 0.95 |
After | 0.89 | 0.78 | 0.93 | 0.96 |

# Conclusion
1. Based on the correlation table of features for stroke, the features with the highest correlation are Age, Heart Disease, Average Glucose Level, and Hypertension.
2. The older a person is, the more likely they are to have a stroke.
3. From the EDA, the number of people who do not have heart disease is higher, but the percentage of having a stroke is higher for someone who has heart disease.
4. From the EDA, the older you are, the higher the Everage Glucose Level and someone with a higher Everage Glucose Level tends to be more likely to have a stroke.
5. From the EDA, it's the same as Heart Disease that in the data someone who has hypertension is less than those who don't, but the potential for someone with hypertension has a higher risk of stroke.
6. In the KNN model, after hyperparameter tuning, a recall score of 93% was obtained.
