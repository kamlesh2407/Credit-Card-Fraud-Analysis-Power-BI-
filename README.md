# 💳 Credit Card Fraud Analysis - (Power BI)

## 📘 Overview
This Power BI project focuses on **analyzing and detecting fraudulent credit card transactions** using the [Credit Card Fraud Detection Dataset] (https://github.com/pianalytix/Credit-Card-Fraud-Risk-Analysis-End-to-End-Power-BI-Project-Data-Analytics-Visualization).  

The goal is to build a data-driven fraud detection system that identifies **high-risk merchants, customers, and transactions**, helping financial institutions take proactive measures against fraud.

---

## 🎯 Objectives
- Detect and monitor fraudulent credit card transactions.  
- Identify **high-risk merchants** (fraud rate > 5%) and customer behavior patterns.  
- Visualize fraud distribution across **geographies, card types, and merchant categories**.  
- Provide actionable insights for fraud prevention and risk management.  

---

## 🧩 Dataset Information
- **Source:** [Credit Card Fraud Detection Dataset] (https://github.com/pianalytix/Credit-Card-Fraud-Risk-Analysis-End-to-End-Power-BI-Project-Data-Analytics-Visualization)
- **Rows:** ~1000 transactions  
- **Key Fields:** 'Transaction ID', 'Customer Name', 'Merchant Name', 'Transaction Date',
       'Transaction Amount (INR)', 'Fraud Risk', 'Fraud Type', 'State',
       'Card Type', 'Bank', 'IsFraud', 'Fraud Score', 'Transaction Category',
       'Merchant Location'

---

## 📊 Dashboard Pages

### **1️⃣ Fraud Overview Dashboard**
- KPIs: Total Transactions, Fraud Transactions, Fraud Amount, Fraud Rate (%)  
- Fraud trend over time (monthly breakdown)  
- Fraud distribution by **State** (map visualization)  
- Fraud type comparison (donut chart)  
- Top 5 Fraudulent Transactions (detail table)

### **2️⃣ Merchant & Customer Analysis**
- KPIs: High-Risk Customers, High-Risk Merchants, Fraud Rate (%)  
- Top 5 Merchant Categories by Fraud Amount
- Top 3 States by Fraudulent Amount  
- Fraudulent Transactions by **Card Type**
- Identification of High Risk Customers with **Risk Level > High** And **Risk Level > Critical**

---

## 📈 Key Metrics & DAX Measures
| Metric | Description | Sample DAX Formula |
|--------|--------------|--------------------|
| **Fraud Rate (%)** | % of total transactions that are fraudulent | `DIVIDE([Fraud Transactions], [Total Transactions], 0)` |
| **Fraud Risk Score** | Categorizes fraud rate into risk levels | `SWITCH(TRUE(), [Fraud Rate] > 20, "Critical", [Fraud Rate] > 10, "High", [Fraud Rate] > 5, "Medium", "Low")` |
| **High-Risk Merchants** | Count of customers with Fraud Risk Level = Critical and High | `COUNTROWS(FILTER(SUMMARIZE(Risk Level, "Risk Level", [Fraud Rate]), [Rate] >0R("High","Critical"))` |
| **High-Risk Merchants** | Count of merchants with Fraud Rate > 5% | `COUNTROWS(FILTER(SUMMARIZE(Merchant[ID], "Rate", [Fraud Rate]), [Rate] > 0.05))` |

---

## 🧠 Insights & Findings
- **E-commerce and Food Delivery** merchants had the highest fraud volume.  
- **Fraud spikes** between May and August, showing possible seasonal patterns.  
- **Visa and Mastercard** accounted for the majority of fraudulent transactions.  
- **West Bengal, Telangana and Uttar Pradesh** recorded the highest fraudulent transaction amounts.  
- Merchants with low transaction volumes but high fraud percentages were flagged as **critical risk**.

---

## ⚙️ Tools & Skills Used
- **Power BI:** Power Query, Dashboard Design, Data Modeling, DAX, Drillthrough  
- **Excel / CSV:** Data Cleaning and Preprocessing  
- **Data Storytelling:** KPI Design, Fraud Trend Visualization  
- **Analytical Techniques:** Fraud Rate Calculation, Risk Segmentation, Comparative Analysis  

---

## 🚀 Future Enhancements
- Integrate a **Machine Learning model** (Logistic Regression / Random Forest) for predictive fraud scoring.  
- Implement **real-time fraud alerts** using Power BI Streaming datasets.  
- Add a **drillthrough page** for detailed Merchant & Customer profiles.  

---

## 📸 Dashboard Previews

### 🧾 Fraud Overview Dashboard
![Fraud Overview Dashboard]<img width="1328" height="749" alt="image" src="https://github.com/user-attachments/assets/46706cf4-2738-42a5-bc72-71fe81ef9dbb" />


### 🧍 Merchant & Customer Analysis
![Merchant & Customer Analysis]<img width="1329" height="752" alt="image" src="https://github.com/user-attachments/assets/6a919aea-d05c-4e82-be82-6a8830646732" />


---

## 📎 Repository Structure
