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
