# Bank Customer Churn Prediction

## Project Overview

This repository contains a machine learning model for predicting customer churn in the banking sector. The project uses a dataset of bank customers, including various features like demographic information, account details, and financial data, to predict whether a customer will churn (leave the bank).

The project leverages **Snowflake** for data management, feature engineering, and machine learning lifecycle management, utilizing **Snowflake ML** to streamline the process of model training, deployment, and inference. Snowflake’s features like **Role-based Access Control (RBAC)** and **Snowflake ML** provide a secure and scalable environment to build and manage machine learning models.

### Key Highlights:
- **Data Management**: Snowflake is used for storing and processing data, ensuring secure access and scalability.
- **Feature Engineering**: Feature views are created in Snowflake to transform and prepare data for training.
- **Machine Learning Pipeline**: Snowflake ML facilitates the full lifecycle of the model, including data processing, training, model management, and deployment.
- **Model Selection**: The **XGBClassifier** (XGBoost Classifier) is used to predict customer churn, achieving an accuracy of **87%**.
- **Model Registry**: Snowflake ML includes model registry functionality for versioning, tracking, and managing multiple models.

This project demonstrates the seamless integration of Snowflake's tools to build a scalable and maintainable churn prediction system, from feature engineering to real-time inference.

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

# Step-by-Step Guide to Running Bank Customer Churn Prediction in Snowflake

This guide explains how to run the **Bank Customer Churn Prediction** project using **Snowflake Notebooks**.

## Prerequisites
- Access to a **Snowflake account** and **Snowflake Notebooks**.
- Appropriate **roles and permissions** to create and manage Snowflake objects.

## Step 1: Set Up Snowflake Environment
1. **Import Notebooks**: Import the following notebooks into **Snowflake Notebooks**:
   - `01_INITIATION_BANK_CHURN.ipynb`
   - `02_EDA_BANK_CHURN.ipynb`
   - `03_FEATURE_VIEW_BANK_CHURN.ipynb`
   - `04_TRAINING_BANK_CHURN.ipynb`
   - `05_INFERING_BANK_CHURN.ipynb`
   
2. **Run `01_INITIATION_BANK_CHURN.ipynb`**:
   - This notebook creates the required **roles**, **warehouses**, and **database objects** for the project.

## Step 2: Run Notebooks in Sequence
1. **Run `02_EDA_BANK_CHURN.ipynb`**: Perform exploratory data analysis (EDA) on the dataset.
2. **Run `03_FEATURE_VIEW_BANK_CHURN.ipynb`**: Create feature views in Snowflake for training the model.
3. **Run `04_TRAINING_BANK_CHURN.ipynb`**: Train the **XGBClassifier** model.
4. **Run `05_INFERING_BANK_CHURN.ipynb`**: Make predictions using the trained model.
