# Customer Churn Analysis

This repository provides an end-to-end demonstration of how to analyze and understand the key factors influencing customer churn in a banking institution. By identifying the primary drivers behind churn, the bank can implement targeted strategies to enhance customer retention, improve service delivery, and mitigate potential revenue losses.

---

## Table of Contents
1. [Project Overview](#project-overview)  
2. [Business Requirements](#business-requirements)  
3. [Data Requirements](#data-requirements)  
4. [Analysis Workflow](#analysis-workflow)  
5. [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)  
6. [Results & Insights](#results--insights)  
7. [Quick-Win Strategies](#quick-win-strategies)  
8. [How to Use](#how-to-use)  
9. [Conclusions](#conclusions)  

---

## Project Overview

**Purpose of the Study**  
The primary objective is to analyze customer churn in a banking context. Customer churn refers to the percentage of clients who discontinue using the bank's services over a given period. Reducing churn is crucial for maintaining a strong customer base and revenue stability.

**Key Research Question**  
> *What are the primary factors influencing customer churn in the bank?*

By answering this question, the bank can design data-driven strategies to proactively address potential churn risks.

---

## Business Requirements

We define **SMART** (Specific, Measurable, Achievable, Relevant, Time-bound) business indicators for churn reduction and customer engagement:

1. **Churn Rate Reduction Goal**  
   - Reduce churn by **10%** by the next financial quarter.

2. **Customer Engagement Improvement**  
   - Increase active bank users by **15%** within six months.

3. **Enhancing Digital Banking Usage**  
   - Increase transactions via the banking app by **20%** within the next quarter.

**Performance Metrics** to track progress:
- **Customer Activity Metrics**: Transaction frequency, online banking logins, ATM withdrawals.  
- **Product Holding Metrics**: Number of financial products used per customer.  
- **Service Complaint Metrics**: Number of complaints per customer and response resolution time.  
- **Customer Satisfaction Score (CSAT)**: Surveys or Net Promoter Score.  
- **Financial Behavior Metrics**: Average account balance, transaction volume.

---

## Data Requirements

The analysis requires structured customer data with the following attributes:

1. **Customer Demographics**  
   - Age  
   - Gender  
   - Marital Status  
   - Income Level  
   - Employment Type  

2. **Banking Behavior**  
   - Account type (savings, checking, investment)  
   - Number of active accounts  
   - Frequency of transactions  
   - Online banking engagement  
   - Credit card usage  
   - Loan history  

3. **Customer Engagement & Support**  
   - Customer complaints filed  
   - Response time to complaints  
   - Satisfaction survey results  

4. **Churn Labels**  
   - Binary indicator denoting whether the customer has churned (`1`) or remains active (`0`)

---

## Analysis Workflow

1. **Data Inspection & Cleaning**  
   - Handled missing values in key fields (e.g., `customer_age`, `registration_dt`).  
   - Converted categorical data into numerical representations for proper analysis.  
   - Examined data for inconsistencies and outliers.

2. **Dataset Sufficiency**  
   - Verified that available features (demographics, banking behavior, engagement, and financial metrics) provide enough information for churn analysis.  
   - Identified the need for more detailed engagement data (e.g., transaction types, loan details, complaint text).

3. **Dealing with Imbalance**  
   - **Churn** labels are imbalanced: most customers do not churn.  
   - Consider oversampling or undersampling techniques (e.g., SMOTE) to improve model performance.

4. **Exploratory Data Analysis (EDA)**  
   - Examined overall churn distribution, correlation among numerical features, and relationships between account balances, product usage, and churn.

---

## Exploratory Data Analysis (EDA)

### 1. Customer Churn Distribution
- The dataset is **imbalanced**. Most customers remain active; a smaller proportion churn.

### 2. Correlation Heatmap
- **`numofproducts`**: Negative correlation with churn (customers holding more products tend to stay).
- **`customer_age`**: Slight positive correlation with churn (older customers may be more likely to leave).
- **`has_mob_app` & `push_flg`**: Negative correlation with churn (users of mobile banking and push notifications are less likely to churn).

### 3. Number of Products vs Churn
- Customers with **1 or 2** products have a higher churn rate.
- Customers with **3 or more** products are less likely to churn.

### 4. Account Balance by Churn Status
- Customers with **low balances** are more likely to churn.
- Low card balances often indicate lower engagement or value placed in the account.

### 5. Distribution of Card Balance for High-Risk Churn Customers
- High-risk customers typically have **very low balances**.

---

## Results & Insights

1. **Portrait of a Churned Customer**  
   - Low transaction frequency.  
   - Limited product usage (often a single account type).  
   - Higher complaint rates with delayed resolution.  
   - Low engagement with digital banking services (e.g., no mobile app usage).

2. **Statistical Analysis**  
   - **T-test** on account balances revealed a significant difference between balances of churned vs. retained customers (`p < 0.00001`).

3. **High-Risk Customers**  
   - Typically have **one product**, a **low card balance**, and have churned (`Exited == 1`).  
   - Proactive outreach to these customers can be a quick win to prevent further churn.

---

## Quick-Win Strategies

1. **Personalized Offers & Promotions**  
   - Provide discounts and rewards to customers with low engagement.

2. **Proactive Customer Support**  
   - Monitor and resolve complaints faster to improve customer satisfaction.

3. **Loyalty Programs**  
   - Reward customers for long-term banking relationships (e.g., multi-product discounts).

4. **Enhancing Digital Banking Experience**  
   - Improve mobile apps and online services to encourage adoption and usage.

5. **Targeted Financial Advisory**  
   - Offer financial education or planning tools to customers with low balances to increase their perceived value.

---

## How to Use

1. **Clone the Repository**
   ```bash
   git clone https://github.com/YourUsername/customer-churn-analysis.git
   cd customer-churn-analysis
   ```

2. **Install Required Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Data Preparation**
   - Place your CSV (`customer churn analysis.csv`) and Excel (`Data base from CSV file.xlsx`) files in the `data/` directory (or update the file paths in the script accordingly).

4. **Run the Python Script**
   ```bash
   python churn_analysis.py
   ```
   - This script will:
     - Load the CSV and Excel files.  
     - Clean and prepare the data.  
     - Generate plots (churn distribution, correlation heatmap, etc.).  
     - Perform t-tests for hypothesis validation.  
     - Export key tables and summaries to an Excel file (`Customer_Churn_Analysis.xlsx`).

5. **Review Outputs**
   - Generated plots will appear in your console or notebook environment.  
   - Summaries and results are saved to the output Excel file for further review.

---

## Conclusions

- **Multiple Products**: Encouraging customers to hold multiple products significantly reduces churn risk.  
- **Balance & Engagement**: Customers with low balances and limited use of digital services are more prone to exit.  
- **Complaint Handling**: Delayed complaint resolution correlates with churn. Prioritizing fast response times enhances retention.  
- **Proactive Strategies**: Targeted promotions, loyalty programs, and improved digital experiences can address churn drivers effectively.

By leveraging these insights, financial institutions can adopt data-driven approaches to enhance customer loyalty, boost satisfaction, and maintain a competitive edge.

---
