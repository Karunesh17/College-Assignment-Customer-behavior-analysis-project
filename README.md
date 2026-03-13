Project Overview

Understanding customer behavior is essential for improving business strategies, increasing customer retention, and maximizing revenue.

This project analyzes customer purchasing patterns using Python to identify spending behavior, discount impact, customer segmentation, and churn risk.

The analysis converts raw customer data into actionable business insights that can help companies improve marketing strategies and customer engagement.

Business Problem

Companies often struggle to answer questions like:

Which customers generate the most revenue?

Do discounts actually increase spending?

Which customers are likely to churn?

How does customer satisfaction affect purchases?

This project answers these questions using data analysis and visualization techniques.

Dataset Information

The dataset contains 350 customer records with the following attributes:
| Feature                  | Description                    |
| ------------------------ | ------------------------------ |
| Customer ID              | Unique identifier              |
| Gender                   | Male / Female                  |
| Age                      | Customer age                   |
| City                     | Customer location              |
| Membership Type          | Bronze / Silver / Gold         |
| Total Spend              | Total money spent              |
| Items Purchased          | Number of items purchased      |
| Average Rating           | Customer satisfaction rating   |
| Discount Applied         | Whether a discount was used    |
| Days Since Last Purchase | Customer activity metric       |
| Satisfaction Level       | Customer satisfaction category |


Project Workflow
1 Data Exploration

Initial exploration was performed to understand the dataset structure.

Tasks performed:

Checked dataset information

Examined first rows

Generated statistical summary

Key functions used:

df.info()
df.head()
df.describe()
2 Data Cleaning

Data quality checks included:

Identifying missing values

Removing rows with missing data

Checking for duplicate records

df.isnull().sum()
df.dropna()
df.duplicated()
3 Customer Segmentation

Customers were segmented based on:

Gender distribution

Membership tiers

Findings showed that customers were distributed across Gold, Silver, and Bronze membership levels.

4 Spending Behavior Analysis

Customer spending was analyzed based on:

Membership type

Gender

Example analysis:

df.groupby("Membership Type")["Total Spend"].mean()
df.groupby("Gender")["Items Purchased"].mean()

This helped identify high-value customer segments.

5 Discount Impact Analysis

The analysis evaluated whether discounts influence purchasing behavior.

df.groupby("Discount Applied")["Total Spend"].mean()

This helped determine whether discounts increase spending or reduce revenue.

6 Customer Retention Analysis (Churn Risk)

Customers were categorized into churn risk groups based on inactivity.

Days Since Last Purchase	Customer Status
≤ 30	Active
31 – 90	Medium Risk
> 90	High Risk

Python function used:

def customer_status(days):
    if days <= 30:
        return "Active"
    elif days <= 90:
        return "Medium Risk"
    else:
        return "High Risk"
Data Visualizations

Several visualizations were created to understand customer patterns.

Charts included:

Membership Distribution

Spending by Membership

Customer Satisfaction Distribution

Age Distribution

Age vs Total Spend

Churn Risk Distribution

Discount vs Items Purchased

Customer Activity Histogram

Libraries used:

Matplotlib

Seaborn

Key Business Insights

Important insights derived from the analysis:

Gold members are the highest spenders, making them the most valuable customer segment.

Male customers purchase more items on average compared to female customers.

Discount usage affects purchasing behavior and may influence revenue.

Customers inactive for long periods show increased churn risk.

Higher satisfaction levels are associated with greater spending.

Business Recommendations

Based on the insights, the following strategies are recommended:

Introduce loyalty rewards for Gold members to retain high-value customers.

Encourage Silver and Bronze customers to upgrade with exclusive offers.

Implement targeted discounts to boost purchase frequency.

Reward frequent buyers with loyalty points or coupons.

Identify and engage medium-risk customers with retention campaigns.

Tech Stack

Python

Pandas

Matplotlib

Seaborn

Jupyter Notebook

Project Structure
Customer-Behavior-Analysis
│
├── customer_data.csv
├── analysis.ipynb
├── README.md
└── visualizations
