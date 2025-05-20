# Customer-Churn-Analysis-with-Power-BI

![Screenshot 2025-05-20 161220](https://github.com/user-attachments/assets/9bbe5a7a-eca5-42c9-bd05-37e039c569f5)


# Problem Statement:
This project focuses on analyzing customer churn for Deutsche Bank, one of Germany’s largest and most prominent financial institutions. Customer churn represents the rate at which clients discontinue their relationship with the bank. By examining churn rates against various demographic, transactional, and behavioral factors, the analysis aims to identify the key drivers of customer attrition. The insights generated will enable Deutsche Bank’s business teams to develop targeted strategies and make data-driven decisions to reduce churn and enhance customer retention.

## Dataset

The data for this project is a CSV file containing 10000 rows and 12 columns and the following columns:

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
3. Removed null values and unnecessary columns (e.g., estimated_salary).
4. Renamed steps and columns for clarity.
5. Checked and updated data types.
6. Replaced binary values with meaningful labels:
7. Credit card: 1 → Owned, 0 → Not Owned.
8. Activity status: 1 → Active, 0 → Inactive.
9. Churn status: 1 → Churned, 0 → Not Churned.

### 2. Feature engineering

1. Age Group: Categorized ages into groups.
2. Credit Score Category: Classified credit scores.
3. Account Balance Category: Grouped balances.


## Data Modeling

### 1. Reference Tables:

1. Created a reference table for Age Group containing distinct values.
2. Created a reference query for Account Balance and removed duplicates.
3. Created a reference query for Credit Score and removed duplicates.
4. Created custom sort order columns — Age Group ID, Account Balance ID, and Credit Scores ID — to enable meaningful and user-defined sorting of Age Group, Account 
  Balance, and Credit Scores in Power BI visualizations.

### 2.Model Relationships:

Set relationships with many-to-one and one-to-many cardinality in the model tab.

### 3.Created Measures:

1. Customers = COUNT('Bank Customer Data'[Customer ID])
2. Customers Lost = CALCULATE(COUNT('Bank Customer Data'[Churn Status]), 'Bank Customer Data'[Churn Status] = "Churned")
3. Churn Rate = 'Bank Customer Data'[Customers Lost] / 'Bank Customer Data'[Customers]


## Visualizations
#### 1. Donut Charts:

- Customers by gender, activity status, credit card status, country, and product ownership.

#### 2. Line and Clustered Column Charts:

- Customers by age group vs. churn rate.
- Customers by credit score vs. churn rate.
- Customers by account balance vs. churn rate.

#### 3. Slicers:

- Added slicer for filtering churn status.

#### 4. Gauge Chart:

- Showed churn rate with target rate as 15 along with maximum and minimum churn rates.

#### 5. KPI:

- Show Total Customers.


#### Snapshot of Not Churned Dashboard



#### Snapshot of Churned Dashboard


## Insights and Findings
### Customer Segmentation

1. Gender:
- Distribution: Male and female customers are nearly equally distributed (45%-55%).
- Churn Behavior: No significant difference in churn rates between genders.

2. Activity Status:
- Active Customers: Constitute 51-55% of the base, with lower churn rates.
- Inactive Customers: Show a higher propensity to churn, indicating an opportunity for re-engagement strategies.

3. Credit Card Ownership:
- With Credit Cards: Majority of customers (~70-75%) own credit cards.
- Without Credit Cards: Display higher churn rates, potentially due to reduced loyalty.

4. Region:
- Country Distribution: Customers are evenly distributed across France, Germany, and Spain.
- Churn Trend: Spain exhibits slightly higher churn rates compared to other regions.

5. Products:
- Preferred Products: Product 1 and Product 2 are most popular (~45-55% adoption).
- Product 3: Has the lowest adoption rate (<3%) and correlates with higher churn.


###  Behavioral Insights

1. Age Groups:
- Major Segment: Customers aged 41-50 form the largest group but have the highest churn rates.
- Lower Churn Groups: Younger customers (21-30) and older customers (61+) are less likely to churn.

2. Credit Scores:
- High-Risk Segment: Customers with credit scores below 600 are most likely to churn.
- Low-Risk Segment: Customers with scores above 800 exhibit the lowest churn rates.

3. Account Balance:
- High Churn Range: Customers with account balances between 100K-200K churn the most.
- Low Churn Range: Balances below 10K or above 200K have significantly lower churn.
