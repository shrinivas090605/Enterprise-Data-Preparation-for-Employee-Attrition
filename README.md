Enterprise Data Preparation for Employee Attrition

Project Overview

This project focuses on preparing an employee attrition dataset for further analysis and machine learning applications.

The project performs important data preprocessing tasks, including missing value handling, duplicate removal, outlier handling, feature engineering, categorical encoding, numerical scaling, and the creation of a reusable preprocessing pipeline.

objectives

The main objectives of this project are:

Import and inspect the employee attrition dataset.
Identify and handle missing values.
Detect and remove duplicate records.
Detect and handle numerical outliers using the IQR method.
Create meaningful HR-related features.
Encode categorical variables.
Scale numerical variables.
Create a reusable preprocessing pipeline using Scikit-learn.
Export the final processed dataset.

Dataset
The project uses the IBM HR Employee Attrition dataset.

Dataset file:

WA_Fn-UseC_-HR-Employee-Attrition.csv

The dataset contains employee-related information such as:

Age
Department
Job Role
Monthly Income
Years at Company
Total Working Years
Job Satisfaction
Training History
Promotion History
Attrition

The target variable is:

Attrition

Technologies Used

The following Python libraries were used:

Pandas
NumPy
Scikit-learn

The project was implemented using a Google Colab environment.

Data Preprocessing Steps
1. Missing Value Handling

Missing values were checked across all columns.

Numerical columns were handled using the median value.
Categorical columns were handled using the most frequent value.

2. Duplicate Record Handling

Duplicate employee records were identified and removed from the dataset.

3. Outlier Detection and Handling

Numerical outliers were detected using the Interquartile Range (IQR) method.

The IQR boundaries were calculated as:

Lower Bound = Q1 - 1.5 × IQR

Upper Bound = Q3 + 1.5 × IQR

Outliers were handled using IQR capping instead of removing employee records.

4. Feature Engineering

The following HR-related features were created:

PromotionRatio
JobChangeRatio
TrainingFrequency
CompanyExperienceRatio
PromotionGap

These features provide additional information about employee career progression, job mobility, training activity, and company experience.

5. Categorical Encoding

Categorical variables were converted into numerical format using:

OneHotEncoder

The encoder was configured with:

handle_unknown='ignore'

This prevents errors when unseen categories are encountered.

6. Numerical Scaling

Numerical variables were standardized using:

StandardScaler

This ensures that numerical features are transformed to a common scale.

Preprocessing Pipeline

A Scikit-learn preprocessing pipeline was created using:

Pipeline
ColumnTransformer
SimpleImputer
StandardScaler
OneHotEncoder

The workflow is:


Raw Dataset
      ↓
Missing Value Handling
      ↓
Duplicate Removal
      ↓
Outlier Detection and Handling
      ↓
Feature Engineering
      ↓
Feature and Target Separation
      ↓
Numerical Processing
      ├── Median Imputation
      └── StandardScaler
      ↓
Categorical Processing
      ├── Most Frequent Imputation
      └── OneHotEncoder
      ↓
Processed Dataset


 Final Output

The final processed dataset is:

processed_employee_attrition.csv

Final dataset status:

Rows: 1,470
Columns: 61
Missing Values: 0
Duplicate Rows: 0

The processed dataset is ready for further analysis and machine learning applications.





