# Telco-Customer-Churn-Analysis
SQL analysis of telecom customer churn using IBM dataset. Explores key churn drivers including contract type, internet service, and payment method, and provides actionable retention insights through exploratory data analysis.
## 📌 Overview

This project analyzes customer churn behavior using SQL to identify key drivers of customer attrition and uncover high-risk segments.

The goal is to translate raw customer data into actionable business insights for improving retention.

## 📊 Dashboard Preview
<img width="782" height="601" alt="Screen Shot 2026-05-12 at 4 27 14 PM" src="https://github.com/user-attachments/assets/801889a4-1d78-4826-92c1-25eace6050a2" />

---

## 📊 Key Insights

### 📉 Overall Churn

* ~26.5% of customers churned
* Indicates a significant retention challenge

---

### 📌 Key Drivers

**Contract Type**

* Month-to-month customers show the highest churn
* Longer contracts significantly improve retention

**Internet Service**

* Fiber optic customers have the highest churn rates

**Payment Method**

* Electronic check users show the highest churn risk

---

### 🔗 High-Risk Segment

* Month-to-month + Fiber optic customers represent the most at-risk group

---

## 💡 Business Recommendations

* Encourage longer-term contracts through incentives
* Investigate fiber optic pricing and service experience
* Promote more stable payment methods (auto-pay options)
* Target high-risk segments with retention campaigns

---

## 🧾 Key SQL Queries

### Overall Churn Rate

```sql
SELECT 
    ROUND(AVG(CASE WHEN churn = 'Yes' THEN 1 ELSE 0 END) * 100, 2) AS churn_rate_percent
FROM churn;
```

### Churn by Contract

```sql
SELECT 
    contract,
    ROUND(AVG(CASE WHEN churn = 'Yes' THEN 1 ELSE 0 END) * 100, 2) AS churn_rate
FROM churn
GROUP BY contract;
```

### Churn by Payment Method

```sql
SELECT 
    payment_method,
    ROUND(AVG(CASE WHEN churn = 'Yes' THEN 1 ELSE 0 END) * 100, 2) AS churn_rate
FROM churn
GROUP BY payment_method;
```

---

## 🛠️ Tools Used

* SQL (MySQL / DB Fiddle)
* Excel (data cleaning + preprocessing)
* GitHub (documentation)

---

## 📌 Conclusion

This analysis identifies clear behavioral and service-related drivers of customer churn. The findings highlight opportunities for targeted retention strategies focused on contract structure, service type, and payment behavior.

---

## 🚀 Next Steps

* Build interactive dashboard (Excel / Power BI)
* Expand analysis with tenure and monthly charges
* Scale project to full dataset environment

