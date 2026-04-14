# 🛒 E-Commerce Customer Churn Analysis & RFM Segmentation

![Python](https://img.shields.io/badge/Python-3.10-blue) ![Power BI](https://img.shields.io/badge/PowerBI-Dashboard-yellow) ![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-orange) ![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

## 📌 Project Overview

End-to-end customer churn analysis on a real UK e-commerce dataset (1M+ transactions).
The project identifies churned customers, segments the customer base using RFM analysis,
builds a churn prediction model, and delivers business recommendations via an interactive Power BI dashboard.

**Business Problem:** 40.8% of customers have not returned after their first or subsequent purchases.
The goal is to identify who is churning, why, and what the business can do about it.

---

## 📂 Project Structure

```
ecommerce-churn-analysis/
│
├── data/                        # Raw dataset (not pushed — see Dataset section)
├── notebooks/
│   ├── 01_e-commerces-churn-analysis    # Churn labeling and ML models
├── outputs/
│   ├── rfm_segments.csv         # Final RFM table with segments and churn labels
│   ├── monthly_revenue.csv      # Monthly revenue aggregation
│   └── country_revenue.csv      # Revenue by country
├── dashboard/
│   └── churn_dashboard.pbix     # Power BI dashboard file
└── README.md
```

---

## 📊 Dataset

**Source:** [Online Retail II — UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/502/online+retail+ii)

- Real UK-based online retail transactions: **2009–2011**
- Raw size: **1,067,371 rows × 8 columns**
- After cleaning: **805,549 rows, 5,878 unique customers**

**Cleaning steps applied:**
- Removed 29.5% null CustomerIDs (guest checkouts)
- Removed cancelled orders (Invoice starting with 'C')
- Removed rows with Quantity ≤ 0 and Price ≤ 0
- Engineered `TotalPrice = Quantity × Price`

---

## 🔍 Key Findings

| Finding | Value |
|---------|-------|
| Total Revenue | $17.74M |
| Total Customers | 5,878 |
| **Churn Rate** | **40.8%** |
| UK Revenue Concentration | 83% |
| Champions (top segment) | 11% of customers → 54% of revenue |
| One-time buyers | 27.6% of all customers |
| Revenue gap (Top vs Median customer) | 677x |

---

## 👥 RFM Segmentation

Customers scored on **Recency, Frequency, Monetary** (1–4 scale) and grouped into 8 segments:

| Segment | Customers | Avg Recency | Avg Frequency | Avg Monetary |
|---------|-----------|-------------|---------------|--------------|
| Champions | 661 | 10 days | 24 orders | $14,568 |
| Loyal Customers | 1,398 | 39 days | 7 orders | $2,852 |
| At Risk | 654 | 213 days | 7 orders | $2,702 |
| Can't Lose Them | 270 | 363 days | 2 orders | $2,069 |
| Lost | 1,332 | 516 days | 2 orders | $593 |

---

## 🤖 Churn Prediction Model

**Churn Definition:** Customers with Recency > 180 days = Churned (1)

| Model | ROC-AUC | Recall (Churners) |
|-------|---------|-------------------|
| Logistic Regression (threshold=0.5) | 0.779 | 69% |
| **Logistic Regression (threshold=0.4)** | **0.779** | **84%** |
| Random Forest | 0.673 | 52% |

**Threshold tuned to 0.4** to maximize recall — missing a churner costs more than a false alarm.

---

## 📈 Power BI Dashboard

3-page interactive dashboard:

- **Page 1 — Executive Overview:** Total Revenue, Customers, Churn Rate, Monthly Trend, Country Revenue
- **Page 2 — Customer Segments:** Segment distribution, Revenue by segment, Avg RFM table
- **Page 3 — Churn Analysis:** Churned vs Active donut, Churn rate by segment, High-value churned customers list

---

## 💡 Business Recommendations

| Segment | Action | Expected Impact |
|---------|--------|----------------|
| Champions | Loyalty program, early access | Protect $9.6M revenue base |
| Can't Lose Them | Urgent win-back campaign | Recover ~$111K (20% return rate) |
| At Risk | Automated re-engagement emails | Prevent further churn before it's too late |
| New Customers | Onboarding + 2nd purchase incentive | Reduce 27.6% one-time buyer rate |
| Lost | Low-cost mass campaign only | Deprioritize — ROI is low |

---

## 🛠 Tech Stack

- **Python** — Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn
- **Power BI** — Dashboard, DAX measures
- **Jupyter Notebook**
- **Git & GitHub**

---

## 👤 Author

- 📧 [tnchikane2003@gmail.com]
- 💼 [www.linkedin.com/in/tejaschikane]
- 🐙 [https://github.com/Professional03]
