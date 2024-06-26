# Recipe Rating Prediction

## Project Overview

This project aims to predict food ratings based on a given dataset of recipe reviews. Utilizing various machine learning models and extensive exploratory data analysis (EDA), the project seeks to identify the most effective model for predicting ratings. The primary dataset consists of user reviews, including numerical, categorical, and textual features, and the objective is to predict the target variable "Rating."

## Table of Contents
- **Project Overview**
- **Dataset**
- **Exploratory Data Analysis**
- **Feature Engineering**
- **Modeling**
- **Evaluation**
- **Conclusion**
- **Setup and Installation**
- **Usage**
- **Acknowledgements**

## Dataset

The dataset comprises two CSV files: `train.csv` and `test.csv`.

- **train.csv**: Contains 13,636 entries and 15 columns.
- **test.csv**: Contains 4,546 entries and 14 columns (excluding the target variable "Rating").

### Columns in the Dataset:
- **ID**
- **RecipeNumber**
- **RecipeCode**
- **RecipeName**
- **CommentID**
- **UserID**
- **UserName**
- **UserReputation**
- **CreationTimestamp**
- **ReplyCount**
- **ThumbsUpCount**
- **ThumbsDownCount**
- **Rating** (only in `train.csv`)
- **BestScore**
- **Recipe_Review**

## Exploratory Data Analysis

During EDA, the following steps were performed:
1. **Data Overview**: Understanding the dataset structure and types of features.
2. **Distribution Analysis**: Analyzing the distribution of the target variable "Rating."
3. **Correlation Analysis**: Examining the correlation between numerical features and the target variable.
4. **Skewness Analysis**: Checking skewness in numerical features.
5. **Visualization**: Using box plots and violin plots to visualize distributions and relationships.

## Feature Engineering

Several new features were created and existing ones were transformed for better model performance:
1. **Datetime Features**: Extracted day of the week and hour of the day from `CreationTimestamp`.
2. **Interaction Features**: Created `TotalInteractions` and `ThumbsRatio` to capture user engagement.
3. **One-Hot Encoding**: Encoded categorical features like `RecipeCode` and `DayOfWeek`.
4. **Text Processing**: Cleaned and vectorized the `Recipe_Review` text using TF-IDF.

## Modeling

Various models were tested to identify the best-performing algorithm for predicting ratings:
1. **Dummy Classifier**: Baseline model.
2. **Logistic Regression**
3. **Decision Tree Classifier**
4. **Bagging Classifier**: Using Decision Tree as the base estimator.
5. **AdaBoost Classifier**
6. **XGBoost Classifier**

### Best Model

The XGBoost classifier demonstrated the highest accuracy and was selected as the final model.

## Evaluation

Model performance was evaluated using accuracy and other metrics like precision, recall, and F1-score. The confusion matrix provided insights into model predictions across different rating classes.

## Conclusion

The XGBoost classifier emerged as the best-performing model for predicting recipe ratings. The project highlights the importance of feature engineering and the impact of class imbalance on model performance.
**Classification Report Insights:**    
**Class Imbalance:** The classification report reveals imbalances in class distributions, particularly for lower-rated classes (0 to 4).    
**Potential Challenges:** Models may struggle to accurately predict lower-rated recipes due to fewer instances in the dataset.

