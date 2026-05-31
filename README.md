# 🏦 Credit Risk & Portfolio Analytics Dashboard

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)
![Excel](https://img.shields.io/badge/Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-CC2927?style=for-the-badge&logo=microsoft-sql-server&logoColor=white)

---

## 📌 Overview

An end-to-end **Credit Risk & Portfolio Analytics Dashboard** built in **Power BI**, analyzing **51,000+ customer records** from a leading Indian bank and CIBIL dataset.

This project helps financial analysts:
- Monitor credit risk
- Track loan portfolio health
- Identify high-risk customers
- Analyze loan performance trends

---

## 🎯 Problem Statement

Banks face challenges in:
- Identifying risky borrowers early
- Tracking missed payments
- Monitoring secured vs unsecured loans
- Generating real-time portfolio insights

This dashboard solves these using Power BI + DAX.

---

## 📊 Dashboard Pages

### 1. Executive Summary
- Total Customers
- Average CIBIL Score
- High Risk Customers
- Portfolio Health Gauge
- Monthly trend analysis

### 2. Risk Analysis
- Credit Score vs Missed Payments (Scatter Plot)
- Risk segmentation (High / Medium / Low)
- Key Influencers visual
- Decomposition Tree

### 3. Portfolio Deep Dive
- Secured vs Unsecured loans
- Loan type analysis
- Loan growth (L6M vs L12M)
- Credit history age distribution

---

## ⚙️ DAX Measures

```dax
Portfolio Health % =
DIVIDE(SUM('Data'[Tot_Closed_TL]), SUM('Data'[Total_TL])) * 100

Risk Score =
DIVIDE(SUM('Data'[Tot_Missed_Pmnt]), SUM('Data'[Total_TL])) * 100

Risk Category =
SWITCH(
    TRUE(),
    [Risk Score] > 30, "High Risk",
    [Risk Score] > 15, "Medium Risk",
    "Low Risk"
)

Credit Utilisation =
DIVIDE(SUM('Data'[Tot_Active_TL]), SUM('Data'[Total_TL]))

Secured Ratio % =
DIVIDE(
    SUM('Data'[Secured_TL]),
    SUM('Data'[Secured_TL]) + SUM('Data'[Unsecured_TL])
) * 100

Loan Velocity =
DIVIDE(
    SUM('Data'[Total_TL_opened_L6M]),
    SUM('Data'[Total_TL_opened_L12M])
)
```

---

## 🏗️ Tech Stack

| Component | Details |
|---|---|
| Tool | Power BI Desktop / Service |
| Dataset | Bank + CIBIL Data |
| Records | 51,000+ |
| Data Model | Star Schema (PROSPECTID join) |
| Transformations | Power Query |
| Visuals | KPI Cards, Gauge, Scatter Plot, Key Influencers |

---

## 📈 Key Insights

- Portfolio Health: **88.75%**
- High Risk Customers: **~5,800**
- Average CIBIL Score: **~679**
- Unsecured loans show higher default risk
- 4+ missed payments → ~68% lower approval rate

---

## 👨‍💻 Author

**Nikhil Sharma**  
B.E. Computer Engineering | University of Mumbai | 2026  
[LinkedIn](#) | [GitHub](#)
