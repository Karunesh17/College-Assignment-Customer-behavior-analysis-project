# Customer Behavior Analysis Project

A comprehensive data analysis project examining customer segmentation, spending patterns, and retention metrics to drive business insights and recommendations.

## 📋 Table of Contents
- [Overview](#overview)
- [Dataset](#dataset)
- [Project Structure](#project-structure)
- [Key Findings](#key-findings)
- [Business Insights](#business-insights)
- [Recommendations](#recommendations)
- [Visualizations](#visualizations)
- [Installation](#installation)
- [Usage](#usage)

## 📊 Overview

This project analyzes customer data to understand behavior patterns, identify high-value customers, and assess churn risk. Through exploratory data analysis and visualization, we derive actionable business insights for customer retention and revenue optimization.

## 📁 Dataset

The dataset contains **350 customer records** with the following features:

| Column | Type | Description |
|--------|------|-------------|
| Customer ID | int64 | Unique customer identifier |
| Gender | object | Customer gender (Male/Female) |
| Age | int64 | Customer age |
| City | object | Customer location |
| Membership Type | object | Gold/Silver/Bronze membership tier |
| Total Spend | float64 | Total spending amount |
| Items Purchased | int64 | Number of items purchased |
| Average Rating | float64 | Customer rating (3.0 - 4.9) |
| Discount Applied | bool | Whether discount was applied |
| Days Since Last Purchase | int64 | Inactivity duration |
| Satisfaction Level | object | Satisfied/Neutral/Unsatisfied |

### Data Quality
- **Total Records**: 350 entries
- **Missing Values**: None (after cleaning)
- **Duplicate Records**: 0
- **Data Types**: 4 object, 4 int64, 2 float64, 1 bool

## 📂 Project Structure

```
├── customer_data.csv           # Main dataset
├── analysis.py                 # Data analysis and visualization code
└── README.md                   # Project documentation
```

## 🔍 Key Findings

### Customer Segmentation
- **Gender Distribution**: Nearly equal split (Male: 50%, Female: 49.4%)
- **Membership Distribution**: Balanced across all tiers
  - Gold: 117 customers
  - Silver: 117 customers
  - Bronze: 114 customers

### Spending Analysis
- **Average Spending by Membership**:
  - Gold: $1,311.14 (highest)
  - Silver: $748.43
  - Bronze: $474.22 (lowest)
  
- **Gender-based Item Purchases**:
  - Males: 14.4 items on average
  - Females: 10.8 items on average

### Discount Impact
- **Without Discount**: $909.01 average spending
- **With Discount**: $787.27 average spending
- *Note: Counterintuitive finding - discounts associated with lower average spend*

### Customer Retention & Churn Risk
- **Active Customers** (≤30 days): 224 (64%)
- **Medium Risk** (31-90 days): 124 (35.4%)
- **High Risk** (>90 days): Minimal

### Customer Satisfaction
- **Satisfied**: 128 customers
- **Neutral**: 107 customers
- **Unsatisfied**: 115 customers

## 💡 Business Insights

✅ **Gold membership customers demonstrate the highest spending behavior** with an average spend of $1,311.14 compared to Silver ($748.43) and Bronze ($474.22) tiers.

✅ **Male customers purchase more items on average** (14.4 items vs 10.8 for females), indicating different shopping patterns across genders.

✅ **Customer satisfaction correlates strongly with spending**, suggesting that satisfied customers are more likely to make purchases.

✅ **Age-based purchasing power shows variation**, with certain age groups demonstrating higher spending capacity.

✅ **64% of customers are currently active**, indicating relatively good customer retention, though 35% fall into the medium-risk category requiring attention.

## 📈 Recommendations

### 1. **Loyalty Program Enhancement**
Target high spenders with premium loyalty programs and provide strategic discount incentives to low-spending customers to increase their lifetime value.

### 2. **Membership Upgrade Campaign**
Encourage Silver and Bronze customers to upgrade to Gold membership by offering exclusive perks, early access to products, or tiered discount structures.

### 3. **Personalized Discount Strategy**
Implement targeted discounts for high-value customers to increase purchase frequency, focusing on maintaining their engagement rather than solely on price reduction.

### 4. **Rewards-Based Incentive Program**
Create a loyalty point system where customers purchasing higher quantities receive rewards that can be redeemed in future purchases, reducing total order cost while encouraging repeat buying behavior.

### 5. **Churn Prevention Initiative**
Implement re-engagement campaigns for customers in the "Medium Risk" category (31-90 days inactive) with personalized offers and communications.

## 📊 Visualizations

This project includes the following visualizations:

1. **Membership Distribution** - Bar chart showing equal distribution across tiers
2. **Spending by Membership Type** - Revenue comparison across membership levels
3. **Customer Satisfaction Analysis** - Distribution of satisfaction levels
4. **Age Distribution** - Histogram showing customer age demographics
5. **Age vs Total Spend** - Scatter plot revealing age-spending relationships
6. **Customer Retention Analysis** - Churn risk distribution
7. **Impact of Discounts** - Box plot comparing items purchased with/without discounts
8. **Customer Activity Distribution** - Histogram of days since last purchase

## 🛠️ Installation

### Prerequisites
- Python 3.7+
- pip or conda

### Required Libraries
```bash
pip install pandas matplotlib seaborn
```

### Key Code Sections

**Data Loading & Exploration**
```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

df = pd.read_csv("customer_data.csv")
df.info()
df.describe()
```

**Customer Segmentation**
```python
df['Gender'].value_counts()
df['Membership Type'].value_counts()
```

**Spending Analysis**
```python
df.groupby("Membership Type")["Total Spend"].mean()
df.groupby("Gender")["Items Purchased"].mean()
```

**Churn Risk Assessment**
```python
def customer_status(count_days):
    if count_days <= 30:
        return "Active"
    elif count_days <= 90:
        return "Medium Risk"
    else:
        return "High Risk"

df["Churn Risk"] = df["Days Since Last Purchase"].apply(customer_status)
```

**Last Updated**: 2026 | **Status**: Complete ✅
