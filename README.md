# Diabetes Prediction Using Neural Networks and Data Preprocessing Techniques

## Project Overview

This project was completed as part of the Developer Academy Data Science Bootcamp. The aim was to build a machine learning model that predicts whether a patient is likely to have diabetes based on diagnostic health measurements.

The project demonstrates a full machine learning workflow, including data exploration, cleaning, class balancing, feature scaling, neural network development, and model evaluation.

## Dataset

The project used the Pima Indians Diabetes Dataset, which originally contained 768 patient records.

Features included:

* Pregnancies
* Glucose
* Blood Pressure
* Skin Thickness
* Insulin
* BMI
* Diabetes Pedigree Function
* Age

Target variable:

* Outcome

  * 0 = No Diabetes
  * 1 = Diabetes

## Data Cleaning and Preprocessing

Some features contained zero values that were unlikely to represent genuine medical measurements. These were treated as missing values.

Columns checked for zero values:

* Glucose
* Blood Pressure
* Skin Thickness
* Insulin
* BMI

To improve data quality and class balance:

* Rows with the highest number of missing values were removed from the majority class.
* The dataset was reduced from 768 rows to 536 rows.
* Remaining zero values were replaced using median imputation.
* Min-Max scaling was applied to normalise the feature values.
* The data was split into 80% training and 20% testing sets using stratification.

## Exploratory Data Analysis

A correlation heatmap was used to examine relationships between the features and diabetes outcome.

The strongest relationships with diabetes outcome were found in:

* Glucose
* Age

This suggested that glucose level and age were important indicators in predicting diabetes risk.

## Model

A feed-forward neural network was built using TensorFlow/Keras.

Architecture:

* Dense layer with 16 neurons and ReLU activation
* Dense layer with 8 neurons and ReLU activation
* Output layer with 1 neuron and sigmoid activation

Configuration:

* Optimiser: Adam
* Loss function: Binary Crossentropy
* Epochs: 50
* Batch size: 16

## Results

The model achieved the following performance on the test set:

| Metric      | Score |
| ----------- | ----: |
| Accuracy    | 81.5% |
| Precision   | 79.3% |
| Recall      | 85.2% |
| F1 Score    | 82.1% |
| Specificity | 77.8% |

## Confusion Matrix

| Actual / Predicted | No Diabetes | Diabetes |
| ------------------ | ----------: | -------: |
| No Diabetes        |          42 |       12 |
| Diabetes           |           8 |       46 |

The model correctly identified 46 diabetic patients and 42 non-diabetic patients. The recall score of 85.2% indicates that the model detected the majority of diabetes cases in the test set.

## Skills Demonstrated

* Python programming
* Data cleaning
* Exploratory data analysis
* Missing value handling
* Class balancing
* Median imputation
* Feature scaling
* Neural network modelling
* Binary classification
* Model evaluation
* Healthcare data analysis

## Technologies Used

* Python
* Pandas
* Matplotlib
* Seaborn
* Scikit-learn
* TensorFlow/Keras
* Jupyter Notebook

## Future Improvements

Possible improvements include:

* Comparing the neural network against Logistic Regression and Random Forest models
* Using cross-validation for more robust evaluation
* Adding ROC-AUC analysis
* Testing alternative class balancing methods such as SMOTE
* Creating a simple Streamlit web app for user predictions

## Conclusion

This project demonstrates how machine learning can be applied to healthcare-style data to predict diabetes outcomes. Through data cleaning, balancing, scaling, and neural network modelling, the final model achieved 81.5% accuracy and 85.2% recall on the test set.

