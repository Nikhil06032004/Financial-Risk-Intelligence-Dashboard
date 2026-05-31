# 💳 Financial Transactions & Loans Dashboard

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)
![Excel](https://img.shields.io/badge/Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-CC2927?style=for-the-badge&logo=microsoft-sql-server&logoColor=white)

---

## 📌 Overview

An interactive **Financial Transactions & Loans Dashboard** built in **Power BI**, analyzing **5,000+ transactions** across multiple branches, account types, and date ranges.

This dashboard helps financial teams and analysts:
- Monitor loan portfolio size and interest rates
- Compare Credit vs Debit transaction volumes
- Track transaction trends over time (2000–2025)
- Analyze branch-level and customer-level loan distribution

---

## 🎯 Problem Statement

Financial institutions struggle with:
- Getting a unified view of transactions across branches
- Tracking loan distribution per customer over time
- Comparing debit vs credit activity at scale
- Identifying transaction volume trends year over year

This dashboard solves these by combining slicers, KPI cards, and multi-visual analysis in one interactive Power BI report.

---

## 📊 Dashboard Visuals

### 🔢 KPI Cards (Top Row)
| Metric | Value |
|---|---|
| Average Interest Rate | 9.99% |
| Total Loan Amount | $2,545M |
| Avg Transaction Amount | $0.25M |
| Total Transaction Amount | $1,240M |
| Total No. of Transactions | 5,000 |

---

### 📈 Visual Breakdown

#### 1. Total Amount by Branch Name and Transaction Type
- Clustered bar chart comparing **Credit vs Debit** across all branches
- X-axis: Branch Names | Y-axis: Sum of Amount (up to $50,000K)
- Helps identify which branches drive the most transaction volume

#### 2. Loan Amount by Customer Over Time
- Bubble/scatter chart showing **loan distribution per customer**
- X-axis: Time | Y-axis: Loan Amount (up to $1,000K)
- Bubble size/color represents customer segments
- Useful for spotting high-value customers and loan growth patterns

#### 3. Count of Transactions by Transaction Type (Donut Chart)
- **Debit:** 2.49K (49.78%)
- **Credit:** 2.51K (50.22%)
- Near-equal split indicating balanced transaction activity

#### 4. Count of Transactions by Year (Line Chart)
- Trend from **2000 to 2025**
- Peak years visible around **2008–2010** (~220+ transactions)
- Notable dip around **2015–2017** (~142 transactions)
- Recovery trend visible post-2020

---

## 🎛️ Filters & Slicers

| Slicer | Options |
|---|---|
| Transaction Type | Credit / Debit |
| Transaction Date | Date range: 1/4/2000 – 12/28/2025 |
| Loan Amount | Range slider: $10,028.01 – $999,660.85 |
| Account Type | Dropdown (All / specific types) |

> All slicers are cross-filtered — selecting any value updates all visuals simultaneously.  
> **"Apply all slicers"** and **"Clear all slicers"** buttons for quick reset.

---

## ⚙️ DAX Measures

```dax
Total Loan Amount =
SUM('Transactions'[LoanAmount])

Avg Interest Rate =
AVERAGE('Transactions'[InterestRate])

Total Transaction Amount =
SUM('Transactions'[TransactionAmount])

Avg Transaction Amount =
AVERAGE('Transactions'[TransactionAmount])

Total Transactions =
COUNTROWS('Transactions')

Credit Count =
CALCULATE(COUNTROWS('Transactions'), 'Transactions'[TransactionType] = "Credit")

Debit Count =
CALCULATE(COUNTROWS('Transactions'), 'Transactions'[TransactionType] = "Debit")

Credit % =
DIVIDE([Credit Count], [Total Transactions]) * 100

Debit % =
DIVIDE([Debit Count], [Total Transactions]) * 100
```

---

## 🏗️ Tech Stack

| Component | Details |
|---|---|
| Tool | Power BI Desktop |
| Dataset | Financial Transactions & Loans Data |
| Records | 5,000+ Transactions |
| Date Range | 2000 – 2025 |
| Transformations | Power Query |
| Data Model | Relational (Branch, Customer, Transaction) |
| Visuals | KPI Cards, Gauge, Bar Chart, Donut Chart, Bubble Chart, Line Chart |

---

## 📈 Key Insights

- **50/50 split** between Credit and Debit transactions — balanced portfolio
- **$2,545M** total loan book across all customers and branches
- Average interest rate stable at **9.99%**
- Transaction volumes peaked around **2008–2010** and show recovery post-2020
- Some customers hold loans close to **$1M**, indicating high-value segments
- Branch-level data reveals concentration of activity in specific locations

---
<img width="693" height="379" alt="image" src="https://github.com/user-attachments/assets/289380b6-b2fb-460c-88eb-f538e0e4be25" />

## 👨‍💻 Author

**Nikhil Sharma**  
B.E. Computer Engineering | University of Mumbai | 2026  
[LinkedIn](#) | [GitHub](#)
