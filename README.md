# Loan-Analysis-and-Default-Prediction

# Notebook
- You can access the notebook [here](https://github.com/VincentAbas/Loan-Analysis-and-Default-Prediction/blob/51dc1915d40055dac8ce1d732a2fa83601282cd4/Loan_Analysis_and_Default_Prediction.ipynb)
# Data
- You can get the data [here](https://www.kaggle.com/datasets/prakashraushan/loan-dataset)

## Data Descriptions

- customer_id: Unique identifier for each customer
- customer_age: Age of the customer
- customer_income: Annual income of the customer
- home_ownership: Home ownership status (e.g., RENT, OWN, MORTGAGE)
- employment_duration: Duration of employment in months
- loan_intent: Purpose of the loan (e.g., PERSONAL, EDUCATION, MEDICAL, VENTURE)
- loan_grade: Grade assigned to the loan
- loan_amnt: Loan amount requested
- loan_int_rate: Interest rate of the loan
- term_years: Loan term in years
- historical_default: Indicates if the customer has a history of default (Y/N)
- cred_hist_length: Length of the customer's credit history in years
- Current_loan_status: Current status of the loan (DEFAULT, NO DEFAULT)

- Data Shape: 32,574 records

## Columns with missing values:
- customer_id = 3
- employment_duration = 895
- loan_amnt = 1
- loan_int_rate = 3116
- historical_default = 20737
- Current_loan_status = 4

# Data Preperation
## Using KNN for Imputation and Removing Null Values
  - I used KNN for imputing employment_duration and loan_int_rate's null values
  - Removed the records with the missing values in customer_id and loan_amnt

## Adding a new category in historical_default column called "no_records"
- Upon inspecting It seems that the records that have null values in historical_default also fall into the category 'NO DEFAULT' in current_loan_status.
  Therefore it is indicating that its their first time borrowing.

# Data Analysis

## Executive Summary

## Visualizations and Insights
- Dashboard:<img width="946" height="543" alt="Dashboard" src="https://github.com/user-attachments/assets/6dab9e97-6832-4150-9b6a-7b4a99780c4e" />

  You can get the Power BI files [here](https://github.com/VincentAbas/Loan-Analysis-and-Default-Prediction/blob/fa513bfe5eccd6ffb07334bd5b70ab864fcafccc/Loan%20Data%20Analysis.pbix)
  
### Distribution
<img width="628" height="483" alt="Distribution" src="https://github.com/user-attachments/assets/8f90ba29-ce4b-46d1-a35c-58e59d385ff4" />


### Home Ownership
<img width="745" height="488" alt="Home Ownership" src="https://github.com/user-attachments/assets/19e15c9b-7db1-4e60-b1fa-8434069e63a5" />


### Loan Intent
<img width="704" height="480" alt="Loan Intent" src="https://github.com/user-attachments/assets/e7ebb77a-63b4-4aa7-86bf-75aee038a2b0" />



## Recommendations

# Training Machine Learning Models

## Data Preperation

## Training

## Evaluation
