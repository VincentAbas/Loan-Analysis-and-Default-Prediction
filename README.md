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

- Data analysis shows that 21% of borrowers have defaulted, while 79% have not. Most defaults occur among renters, followed by mortgage holders. Debt consolidation and medical     loans make up the majority of defaults. Renters may be more vulnerable due to unexpected financial hardships such as job loss, medical bills, or budgeting challenges, while      borrowers taking debt consolidation or medical loans may already be financially strained. These findings highlight key borrower segments to monitor for potential risk.

## Visualizations and Insights
- Dashboard:<img width="946" height="543" alt="Dashboard" src="https://github.com/user-attachments/assets/6dab9e97-6832-4150-9b6a-7b4a99780c4e" />

  To interact with the dashboard, you can get the Power BI files [here](https://github.com/VincentAbas/Loan-Analysis-and-Default-Prediction/blob/fa513bfe5eccd6ffb07334bd5b70ab864fcafccc/Loan%20Data%20Analysis.pbix)
  
### Distribution
<img width="628" height="483" alt="Distribution" src="https://github.com/user-attachments/assets/8f90ba29-ce4b-46d1-a35c-58e59d385ff4" />

- The distribution looks good as it shows 79% on borrowers that haven't default yet and 21% on borrowers that defaulted.
### Home Ownership
<img width="745" height="488" alt="Home Ownership" src="https://github.com/user-attachments/assets/19e15c9b-7db1-4e60-b1fa-8434069e63a5" />

- Renting appears to be a significant factor in predicting borrower default. The data shows that most defaults occur among individuals who are renting, followed by those with a    mortgage. Renters may be more likely to default due to unexpected financial hardships, such as job loss, poor financial management, or medical expenses, which can quickly        increase their monthly obligations.
  
### Loan Intent
<img width="704" height="480" alt="Loan Intent" src="https://github.com/user-attachments/assets/e7ebb77a-63b4-4aa7-86bf-75aee038a2b0" />

- Debt consolidation and medical bills account for the majority of defaults in the dataset because these types of loans often arise from existing financial stress. Borrowers       taking on debt consolidation may already have multiple outstanding obligations, making it harder to keep up with payments. Similarly, medical expenses are often unexpected and   can be substantial, straining monthly budgets and increasing the likelihood of default.

## Recommendations
- Strengthen Credit Assessment: Incorporate rental status, existing debt, and loan purpose into risk scoring to identify higher-risk borrowers early.

- Offer Financial Counseling: Provide guidance on budgeting and managing unexpected expenses to help borrowers stay on track. This will not only help the borrowers
  but will you will also gain their trust.

- Flexible Repayment Plans: Allow temporary adjustments or hardship programs for borrowers facing job loss, medical bills, or other financial shocks. As this provides relief       during financial hardships, preventing temporary issues from turning into full defaults.

- Monitor High-Risk Loan Types: Keep a closer watch on debt consolidation and medical loans, as these show higher default rates.

- Early Warning Systems: Use predictive analytics to flag borrowers showing signs of financial stress before defaults occur. As this allows you to act before a default             occur minimizing the losses early.

  
# Training Machine Learning Models

## Data Preperation
  - Turned categorical data into numerical data such as:
    - home_ownership
    - loan_intent
    - loan_grade
    - historical_default
    - Current_loan_status
      
## Training
  - I split the data into 80% Traning set and 20% Testing set
  - I trained multiple machine learning model such as (Random Forest, Decision Tree, Logistic Regression, KNeighborsClassifier, and SVC) while also using their default
    Hyperparameters.
    
    <img width="568" height="860" alt="Training Machine Learning Model Code Snippet" src="https://github.com/user-attachments/assets/f4805173-5b9b-4bdd-9b37-ca30df5c1aca" />

    
## Evaluation
  - The Results are great being Random Forest in the lead with 97% accuracy and AUC score of 99%.
  - The results are as follows:
    
  ### Random Forest:
  
  <img width="461" height="577" alt="Random Forest" src="https://github.com/user-attachments/assets/839fa3cf-599d-4be1-a27c-9a8844e8e173" />

  ### Decision Tree:

  <img width="475" height="585" alt="Decision Tree" src="https://github.com/user-attachments/assets/dfdad101-600c-458c-94b0-660d7acc0634" />

  ### SVM:
  
  <img width="462" height="586" alt="SVM" src="https://github.com/user-attachments/assets/0e8c971a-6e87-418b-a555-0b55f65d5487" />

  ### KNN: 
  
  <img width="460" height="577" alt="KNN" src="https://github.com/user-attachments/assets/d96874f1-dc99-422b-81f5-f421bd0043cc" />

  ### Logistic Regression:

  <img width="486" height="582" alt="Logistic Regression" src="https://github.com/user-attachments/assets/84ec435f-7d8b-4413-a286-c21eab2666a1" />

  ### AUC-ROC

  <img width="702" height="557" alt="AUC ROC" src="https://github.com/user-attachments/assets/b9538eeb-595f-412a-a1d3-bb871875a480" />


