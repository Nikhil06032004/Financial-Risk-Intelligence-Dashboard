# 🏦 Credit Risk & Portfolio Analytics Dashboard

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)
![Excel](https://img.shields.io/badge/Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-CC2927?style=for-the-badge&logo=microsoft-sql-server&logoColor=white)

## 📌 Overview

An end-to-end **Banking Credit Risk & Portfolio Analytics Dashboard** 
built in **Power BI**, analysing **51,000+ real customer records** 
from a Leading Indian Bank and CIBIL dataset. This dashboard enables 
financial analysts and risk teams to monitor credit portfolio health, 
identify high-risk customer segments, and track loan performance 
across multiple dimensions.

> **Business Context:** Credit risk monitoring and portfolio analytics 
> are critical functions in banking and financial services. This 
> dashboard replicates the type of analytical reporting used by 
> risk management teams at global investment banks and financial 
> institutions.

---

## 🎯 Problem Statement

Financial institutions managing large credit portfolios face 
challenges in:
- Identifying high-risk borrowers before default occurs
- Monitoring portfolio health across secured and unsecured loans
- Tracking missed payment trends across customer segments
- Reporting credit KPIs to senior stakeholders in real time

This dashboard addresses all four challenges through interactive 
Power BI visualisations backed by advanced DAX calculations.

---

## 📊 Dashboard Pages

### Page 1 — Executive Summary
- Total Customers, Average CIBIL Score, High Risk Count, 
  Average Monthly Income KPI cards
- Portfolio Health Index Gauge (0–100 scale)
- Loan Approval Distribution by Risk Grade
- Month-over-month portfolio trend

### Page 2 — Risk Analysis
- Credit Score vs Missed Payments Scatter Plot 
  (risk mapping by customer segment)
- Dynamic Risk Bucketing (High/Medium/Low) 
  with conditional formatting
- Key Influencers AI Visual — identifies top drivers 
  of loan approval/rejection
- Decomposition Tree — breaks down missed payments 
  by loan type and risk grade

### Page 3 — Portfolio Deep Dive
- Secured vs Unsecured Loan Ratio analysis
- Loan type performance (Auto, CC, Consumer, 
  Gold, Home, Personal Loan)
- New loan velocity — L6M vs L12M comparison
- Age of oldest vs newest trade line distribution

---

## ⚙️ DAX Measures Implemented

```dax
-- Portfolio Health Index
Portfolio Health % =
DIVIDE(
    SUM('Data'[Tot_Closed_TL]),
    SUM('Data'[Total_TL])
) * 100

-- Dynamic Risk Score
Risk Score =
DIVIDE(
    SUM('Data'[Tot_Missed_Pmnt]),
    SUM('Data'[Total_TL])
) * 100

-- Risk Category Bucketing
Risk Category =
SWITCH(
    TRUE(),
    [Risk Score] > 30, "High Risk",
    [Risk Score] > 15, "Medium Risk",
    "Low Risk"
)

-- Credit Utilisation Rate
Credit Utilisation =
DIVIDE(
    SUM('Data'[Tot_Active_TL]),
    SUM('Data'[Total_TL])
)

-- Secured vs Unsecured Ratio
Secured Ratio % =
DIVIDE(
    SUM('Data'[Secured_TL]),
    SUM('Data'[Secured_TL]) + SUM('Data'[Unsecured_TL])
) * 100

-- New Loan Velocity
Loan Velocity =
DIVIDE(
    SUM('Data'[Total_TL_opened_L6M]),
    SUM('Data'[Total_TL_opened_L12M])
)

-- YoY Growth
YoY Growth % =
DIVIDE(
    [Total Active Loans] - CALCULATE(
        [Total Active Loans],
        SAMEPERIODLASTYEAR('DateTable'[Date])
    ),
    CALCULATE(
        [Total Active Loans],
        SAMEPERIODLASTYEAR('DateTable'[Date])
    )
)
```

---

## 🔧 Technical Implementation

| Component | Details |
|---|---|
| **Tool** | Microsoft Power BI Desktop + Power BI Service |
| **Data Source** | Leading Indian Bank + CIBIL Real-World Dataset |
| **Records Analysed** | 51,000+ customer profiles |
| **Data Model** | Star schema — Internal Bank + External CIBIL joined on PROSPECTID |
| **DAX Measures** | 7 custom measures including time intelligence |
| **Power Query** | Data cleaning, null removal, column renaming, data type formatting |
| **Visuals Used** | KPI Cards, Gauge, Scatter Plot, Key Influencers, Decomposition Tree, Waterfall, Bar Chart |
| **Deployment** | Published to Power BI Service with scheduled refresh |
| **Documentation** | Release Notes v1.0 included |

---

## 🗂️ Data Model
Internal_Bank_Dataset
│
│ PROSPECTID (One-to-One)
│
External_CIBIL_Dataset

**Key columns used:**
- `Total_TL` — Total trade lines
- `Tot_Active_TL` — Active loans
- `Tot_Closed_TL` — Closed loans
- `Tot_Missed_Pmnt` — Missed payments
- `Secured_TL / Unsecured_TL` — Loan security type
- `Total_TL_opened_L6M/L12M` — New loan velocity
- `Age_Oldest_TL / Age_Newest_TL` — Credit history depth

---

## 📈 Key Insights Generated

- **88.75% Portfolio Health Index** — indicates strong 
  closed-to-total loan ratio
- **5,882 High Risk Customers** identified through 
  dynamic DAX risk bucketing
- **Average CIBIL Score: 679.86** — borderline 
  fair-to-good credit range
- Unsecured loans show 2.3x higher missed payment 
  rates vs secured loans
- Customers with 4+ missed payments have 
  68% lower approval probability

**Nikhil Sharma**
B.E. Computer Engineering | University of Mumbai | 2026

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin)](https://linkedin.com/in/nikhil-sharma-149211286)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=flat&logo=github)](https://github.com/Nikhil06032004)
