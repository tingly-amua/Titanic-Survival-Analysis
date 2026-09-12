# Titanic-Survival-Analysis

<img width="1164" height="600" alt="csm_titanic1164_887609b912" src="https://github.com/user-attachments/assets/fe9fdd4f-9413-443b-8e1f-fb098bce54b9" />

## Project Overview
The dataset was obtained from [Kaggle](https://www.kaggle.com/datasets/yasserh/titanic-dataset)

This project aims to identify meaningful patterns and relationships within the Titanic dataset. Its primary purpose is to explore whether characteristics such as passenger class, sex, age, and fare were associated with differences in survival outcomes.

This project applies a complete machine learning workflow to the **Titanic passenger dataset** to investigate whether passenger characteristics can be used to predict survival.

The project was undertaken as a **machine learning refresher**, with emphasis on understanding the end-to-end modeling process rather than maximizing predictive performance.

## Objective

> **Can a classification model predict whether a passenger survived the Titanic disaster based on available passenger characteristics?**

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Jupyter Notebook

## Project Structure

```text
Titanic-Survival-Prediction/
│
├── data/
│   └── Titanic-Dataset.csv
│
├── notebooks/
│   └── EDA.ipynb
│   └── Modeling.ipynb
├── README.md
└── Images folder
```

## Dataset

The dataset contains information about Titanic passengers, including:

* Passenger class (`Pclass`)
* Sex
* Age
* Number of siblings/spouses aboard (`SibSp`)
* Number of parents/children aboard (`Parch`)
* Fare
* Port of embarkation (`Embarked`)
* Survival status (`Survived`)

`Survived` was used as the binary target variable.

## Workflow

The project followed these main stages:

1. Data loading and understanding
2. Data cleaning and preprocessing
3. Exploratory data analysis (EDA)
4. Feature and target separation
5. Train-test split
6. Numerical and categorical preprocessing using `ColumnTransformer`
7. Baseline Logistic Regression
8. Decision Tree classification
9. Random Forest classification
10. Hyperparameter tuning using `GridSearchCV`
11. Evaluation using accuracy, precision, recall, F1-score, and confusion matrices
12. Comparison of model performance

## Modeling Approach

A preprocessing pipeline was implemented to ensure that transformations were learned only from the training data.

### Numerical features

* Mean imputation
* Standardization

### Categorical features

* Most-frequent imputation
* One-hot encoding

The following classifiers were evaluated:

* Logistic Regression
* Decision Tree
* Random Forest

Hyperparameter tuning was performed on the Decision Tree and Random Forest using **5-fold cross-validation**.

## Results

| Model               | Test Accuracy |
| ------------------- | ------------: |
| Logistic Regression |        80.00% |
| Decision Tree       |        80.45% |
| Tuned Decision Tree |        80.45% |
| Random Forest       |    **81.01%** |
| Tuned Random Forest |        80.45% |

The untuned Random Forest achieved the highest test accuracy at **81.01%**.

The tuned Random Forest achieved the highest mean cross-validation score at **83.44%**, but its held-out test accuracy was **80.45%**.

### Key Findings

* All evaluated models produced relatively similar performance, with test accuracy around 80–81%.
* The Random Forest provided only a modest improvement over the simpler models.
* Hyperparameter tuning improved cross-validation performance but did not improve final test-set performance.
* The models generally identified non-survivors more effectively than survivors.
* The results demonstrate that increasing model complexity or tuning hyperparameters does not necessarily improve generalization to unseen data.

## Conclusion

The project demonstrates a complete classification workflow, from exploratory analysis and preprocessing through model development, cross-validation, hyperparameter tuning, and final evaluation.

The results suggest that the current feature set provides a reasonable predictive baseline but further model tuning alone is unlikely to produce substantial improvements.   
Future iterations could investigate **feature engineering**, including passenger titles, cabin deck, travelling-alone indicators, family size, and ticket-group information.

The project also reinforced an important machine learning principle: **model performance should be evaluated on unseen data, and a higher cross-validation score does not necessarily translate into better test-set performance.**

## Future Improvements

Potential future work includes:

* Feature engineering
* Feature selection
* Probability calibration
* Alternative classification algorithms
* More extensive model interpretation
* Evaluation using additional metrics beyond accuracy
* Investigation of class-specific performance

## Author

**Kevin Karanja**

BSc Statistics | Data Science & Analytics

This project is part of a data science portfolio focused on applying statistical and machine learning techniques to real-world datasets.
