# Bank Customer Churn Prediction

## Project Overview

This repository contains a machine learning model for predicting customer churn in the banking sector. The project utilizes a dataset of bank customers, including various features like demographic information, account details, and financial data, to identify whether a customer will churn (leave the bank).

The project leverages **Snowflake** for data management, feature engineering, and machine learning lifecycle management, utilizing **Snowflake ML** for seamless integration of model training, deployment, and inference. Snowflake’s features like **Role-based Access Control (RBAC)**, **Data Sharing**, and **Snowflake ML** help manage data securely and build robust ML models at scale.

## Project Files

- **01_INITIATION_BANK_CHURN.ipynb**: Creates necessary roles, warehouses, and database objects in Snowflake to support the project.
- **02_EDA_BANK_CHURN.ipynb**: Exploratory Data Analysis (EDA) for understanding the dataset.
- **03_FEATURE_VIEW_BANK_CHURN.ipynb**: Creates feature views in Snowflake, enabling the generation of feature tables for machine learning models.
- **04_TRAINING_BANK_CHURN.ipynb**: Trains the machine learning model using Snowflake's **Snowpark** or **Snowflake ML**.
- **05_INFERING_BANK_CHURN.ipynb**: Uses the trained model to make predictions on new customer data in Snowflake.
- **Customer_Churn_Analysis.csv**: The dataset containing customer information.
- **environment.yml**: Environment setup for replicating the project.

## Dataset

The dataset, **Customer_Churn_Analysis.csv**, contains the following columns:

| Column              | Description                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| **ID**              | Unique customer identifier                                                   |
| **ClientID**        | Client’s ID number                                                           |
| **Surname**         | Customer's surname                                                           |
| **CreditScore**     | Credit score of the customer                                                 |
| **Geography**       | Country where the customer resides (e.g., France, Spain)                    |
| **Gender**          | Gender of the customer (Male/Female)                                         |
| **Age**             | Age of the customer                                                          |
| **Grade**           | Customer’s grade based on their profile                                      |
| **AccountBalance**  | Account balance of the customer                                              |
| **ProductCount**    | Number of products owned by the customer                                     |
| **OwnsCreditCard**  | Indicates if the customer owns a credit card (0 = No, 1 = Yes)               |
| **IsActive**        | Whether the customer’s account is active (0 = No, 1 = Yes)                   |
| **SalaryEstimated** | Estimated salary of the customer                                             |
| **Churned**         | Target variable (1 = Customer has churned, 0 = Customer has not churned)     |

## Snowflake Integration

### 01_INITIATION_BANK_CHURN.ipynb

This notebook sets up the necessary roles, warehouses, and database objects in **Snowflake** to support the project. It includes creating:

- **Roles**: Define user roles with specific privileges to ensure proper access control and secure handling of data.
- **Warehouses**: Establish virtual warehouses for running queries and ML operations.
- **Databases and Schemas**: Create databases and schemas to organize and store the project data and model artifacts.
  
Snowflake uses **Role-based Access Control (RBAC)** to manage permissions effectively. The required roles might include:

- `DATA_SCIENTIST_ROLE`: For users responsible for training and testing machine learning models.
- `DATA_ENGINEER_ROLE`: For users performing ETL and data manipulation tasks.
- `ML_MODEL_ADMIN_ROLE`: For administering machine learning models within Snowflake.
  
**Example**:

```sql
-- Creating necessary roles for the project
CREATE ROLE IF NOT EXISTS data_scientist_role;
CREATE ROLE IF NOT EXISTS data_engineer_role;
CREATE ROLE IF NOT EXISTS ml_model_admin_role;

-- Granting privileges to the roles
GRANT USAGE ON WAREHOUSE my_warehouse TO ROLE data_scientist_role;
GRANT SELECT ON DATABASE my_database TO ROLE data_engineer_role;
GRANT CREATE MODEL ON DATABASE my_database TO ROLE ml_model_admin_role;
