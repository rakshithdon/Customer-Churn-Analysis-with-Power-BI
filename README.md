# Customer-Churn-Analysis-with-Power-BI

![Image](Screenshot 2025-05-20 161220.png)

# Problem Statement:
This project focuses on analyzing customer churn for Deutsche Bank, one of Germany’s largest and most prominent financial institutions. Customer churn represents the rate at which clients discontinue their relationship with the bank. By examining churn rates against various demographic, transactional, and behavioral factors, the analysis aims to identify the key drivers of customer attrition. The insights generated will enable Deutsche Bank’s business teams to develop targeted strategies and make data-driven decisions to reduce churn and enhance customer retention.

## Dataset

The data for this project is a CSV file containing 1000 rows and 12 columns and the following columns:

### Column	Description
- customer_id = Unique identifier for each customer

- credit_score = Credit score of the customer

- country = Country of the customer

- gender = Gender of the customer

- age =	Age of the customer

- tenure Duration (in years) = the customer has been with the company

- balance = Account balance of the customer

- products_number =	Number of products owned by the customer

- credit_card = Whether the customer owns a credit card (1 = Yes, 0 = No)

- active_member = Whether the customer is an active member (1 = Active, 0 = Inactive)

- estimated_salary = Estimated salary of the customer

- churn =  Whether the customer churned (1 = Yes, 0 = No)


## Data Collection and Preparation

### 1. Connect, Clean, and Transform Data:

1. Imported the dataset into Power Query.
2. Promoted the first row as headers.
3. Removed unnecessary columns (e.g., estimated_salary).
4. Renamed steps and columns for clarity.
5. Checked and updated data types.
6. Replaced binary values with meaningful labels:
7. Credit card: 1 → Owned, 0 → Not Owned.
8. Activity status: 1 → Active, 0 → Inactive.
9. Churn status: 1 → Churned, 0 → Not Churned.

### 2. Created Conditional Columns:

1. Age Group: Categorized ages into groups.
2. Credit Score Category: Classified credit scores.
3. Account Balance Category: Grouped balances.


## Data Modeling

### 1. Reference Tables:

1. Created a reference table for Age Group containing distinct values.
2. Created a reference query for Account Balance and removed duplicates.
3. Created a reference query for Credit Score and removed duplicates.
