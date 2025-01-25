# Wizardry School Enrollment Prediction

## Project Overview
This project focuses on creating a predictive model to determine whether aspiring students are accepted into a prestigious wizardry school. Using a dataset of historical admissions, the goal is to develop a machine learning algorithm that leverages student characteristics, such as gender, financial background, and experience level, to make accurate predictions.

## Objectives
The primary objectives of this project were:
1. Analyze the historical admissions dataset to uncover patterns and insights.
2. Build and evaluate machine learning models to predict student admissions.
3. Optimize the model to achieve high F1-scores, ensuring accuracy and fairness in predictions.
4. Submit final predictions to Kaggle for external evaluation.

## Problem Statement
Admissions to the wizardry school are based on a rigorous selection process, and making accurate decisions is crucial to maintaining fairness and excellence. The challenge was to develop a model capable of predicting admission outcomes using the provided features, overcoming data imbalances and optimizing for performance.

## Methodology
### Dataset
The dataset consists of:
- **Training Set**: Includes features and the admission outcome (0: not admitted, 1: admitted).
- **Test Set**: Contains only features; predictions are to be made for this dataset.

### Features
Key features include:
- **Program**: The program the student applied for.
- **Gender**: Male or Female.
- **Experience Level**: Skill and knowledge level of the student.
- **Financial Background**: Family’s financial status.
- **School of Origin**: The student’s previous school.
- **Admitted in School**: Target variable (1 if admitted, 0 otherwise).

### Data Preprocessing
1. **Exploratory Analysis**:
   - Checked for missing values and data distribution.
   - Visualized numerical and categorical variables for insights.
2. **Handling Missing Values**:
   - Imputed missing values in "Experience Level" using KNNImputer.
   - Dropped "School Dormitory" due to excessive missing values (78.5%).
3. **Encoding**:
   - Used dummy variables for categorical features.
   - Manually encoded binary variables (e.g., gender: Male = 1, Female = 0).
4. **Scaling**:
   - Applied MinMaxScaler (-1, 1) to ensure uniform feature scaling.
5. **Feature Selection**:
   - Used Recursive Feature Elimination (RFE) and LassoCV for feature importance ranking.

### Modeling
1. **Models Tested**:
   - Logistic Regression
   - Decision Tree
   - K-Nearest Neighbors (KNN)
   - Naive Bayes
   - Bagging Classifier
   - Random Forest
   - Gradient Boosting
   - AdaBoost
   - Stacking Classifier
2. **Validation**:
   - Stratified K-Fold cross-validation to evaluate models.
   - F1-score used as the primary performance metric due to dataset imbalance.
3. **Hyperparameter Tuning**:
   - GridSearchCV optimized model parameters.

### Final Model
The **Random Forest Classifier** was chosen as the final model for its:
- High F1-Score on validation (0.7532).
- Balanced performance between training and validation (low overfitting).
- Simplicity and interpretability.

## Results
1. **Top Features**:
   - Gender, Financial Background, Experience Level, and Program were the most influential features.
2. **Model Performance**:
   - Random Forest achieved the highest F1-Score, outperforming other models.
   - Stacking Classifier showed competitive results but was more complex.
3. **Kaggle Submission**:
   - Final predictions achieved an F1-Score of 0.8235 on Kaggle.

## Deliverables
1. **Report**: A comprehensive analysis of the methodology, models, and results.
2. **Jupyter Notebook**: Contains all code for data processing, modeling, and prediction.
3. **CSV File**: Final predictions for the test set (Student ID and admission outcome).
4. **Kaggle Submission**: Evaluated performance on an external leaderboard.

## Conclusion
The project successfully developed a machine learning model to predict wizardry school admissions. Despite challenges like dataset imbalance and missing values, the Random Forest model provided robust and interpretable results. Future improvements could include expanding the dataset and exploring ensemble techniques further.
