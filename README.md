
# Customer Churn Analysis & Retention Strategy

## Overview

This project analyses customer churn at **ABC Communications Ltd** to identify where churn is concentrated, determine the customer profiles requiring priority attention, and translate analytical findings into targeted and measurable retention actions.

Rather than relying only on the overall churn rate, the analysis progressively segments the customer base across **contract type, tenure, Internet service, payment method, and support/security services** to uncover higher-risk customer profiles.

The project was completed as part of the **AnalystLab Africa Data Analytics Internship Programme**.

---

## Business Problem

ABC Communications Ltd is experiencing customer churn, but an overall churn rate alone does not indicate **where management should intervene first**.

The analysis therefore addresses three key business questions:

1. **Where is churn most concentrated?**
2. **Which combination of customer characteristics identifies the highest-risk segment?**
3. **Which retention actions should be tested and monitored?**

---

## Dataset

The analysis uses a telecommunications customer churn dataset containing:

- **7,043 customers**
- **21 variables**
- Customer demographics
- Contract information
- Internet and additional services
- Payment method
- Tenure
- Monthly and total charges
- Churn status

### Data Quality

Dataset inspection identified:

- **0 duplicated rows**
- **0 duplicated customer IDs**
- **11 missing values in `TotalCharges`**

All 11 missing `TotalCharges` values correspond to customers with **tenure = 0**.

These customers were retained because the missing values have a coherent business interpretation: they represent customers at the beginning of their lifecycle who have not yet accumulated historical charges.

---

## Analytical Workflow

The project follows a hybrid analytical workflow:

**Source Dataset → Power BI → Data Preparation → KPI Development → Customer Segmentation → Python Statistical Visualisation → Business Interpretation → Recommendations**

### Power BI

Power BI was used as the primary analytical environment for:

- Data preparation
- KPI development
- Customer segmentation
- Churn analysis
- Risk-profile construction
- Business visualisation
- Decision-oriented dashboard development

### Python

Python was used as a complementary analytical tool for:

- Monthly Charges Box Plot
- Correlation Heatmap
- Statistical exploration of numerical variables

---

## Core KPIs

| KPI | Result |
|---|---:|
| Total Customers | 7,043 |
| Churned Customers | 1,869 |
| Churn Rate | **26.54%** |
| Retention Rate | **73.46%** |

The **26.54% overall churn rate** serves as the analytical baseline.

The objective of the segmentation analysis is to identify customer populations whose churn rate materially exceeds this baseline.

---

# Key Findings

## 1. Contract Type Is a Major Churn Marker

Customers on **Month-to-month contracts** show a churn rate of:

**42.71%**

compared with:

- One-year: **11.27%**
- Two-year: **2.83%**

In addition, **88.6% of churned customers are on Month-to-month contracts**.

This makes contract structure one of the strongest segmentation signals in the analysis.

---

## 2. Churn Is Highest During the First 12 Months

Churn decreases substantially as customer tenure increases.

| Tenure | Churn Rate |
|---|---:|
| 0–12 months | **47.44%** |
| 13–24 months | 28.71% |
| 25–48 months | 20.39% |
| 49–72 months | 9.51% |

The first 12 months therefore represent the main **customer vulnerability window**.

---

## 3. Fiber Optic Customers Show Elevated Churn

Churn varies substantially by Internet service:

| Internet Service | Churn Rate |
|---|---:|
| Fiber Optic | **41.89%** |
| DSL | 18.96% |
| No Internet Service | 7.40% |

Fiber Optic churn is more than twice the DSL churn rate.

This result indicates a priority area for deeper operational investigation, including customer experience, service quality, perceived value, incidents and pricing.

---

# Cumulative Risk Segmentation

The strongest analytical signal emerges when several risk markers are progressively combined.

| Customer Profile | Churn Rate |
|---|---:|
| Overall Population | **26.54%** |
| Month-to-month | **42.71%** |
| + Fiber Optic | **54.61%** |
| + Electronic Check | **60.37%** |
| + Tenure 0–12 months | **71.16%** |

### Priority Segment

The highest-risk customer profile identified in the analysis is:

> **Recently acquired customers on Month-to-month contracts, using Fiber Optic Internet and paying by Electronic Check.**

Their observed churn rate reaches:

# **71.16%**

This is approximately **2.7 times the overall churn rate**.

This segmentation represents an **accumulation of associated risk markers**. It should not be interpreted as proof that any individual characteristic causes churn.

---

## 4. Tech Support and Online Security Reveal a Retention Opportunity

Within the Fiber Optic segment:

| Service Configuration | Churn Rate |
|---|---:|
| Neither TechSupport nor OnlineSecurity | **60.70%** |
| TechSupport only | 42.40% |
| OnlineSecurity only | 39.71% |
| Both services | **28.05%** |

Customers with both **TechSupport and OnlineSecurity** show substantially lower churn than customers with neither service.

This finding supports testing a targeted **Support + Security bundle** for high-risk Fiber Optic customers.

However, this relationship is **associative rather than causal** and should therefore be validated through a controlled business pilot before scaling.

---

# Business Recommendations

## 1. Strengthen Early-Life Retention

Develop a structured onboarding and proactive engagement programme during the **first 12 months**, when customer vulnerability is highest.

## 2. Prioritise Customers with Accumulated Risk

Retention resources should not be distributed uniformly across the customer base.

Priority should be given to customers combining:

- Month-to-month contract
- Fiber Optic service
- Electronic Check payment
- Tenure of 0–12 months

## 3. Test Contract Migration

Test targeted incentives encouraging suitable Month-to-month customers to migrate toward **One-year or Two-year contracts**.

The impact should be measured before scaling the intervention.

## 4. Investigate the Fiber Optic Customer Experience

The elevated Fiber Optic churn rate requires deeper operational diagnosis.

Potential areas for investigation include:

- Network/service quality
- Service incidents
- Customer complaints
- Price-to-value perception
- Installation and onboarding experience
- Support interactions

## 5. Pilot a TechSupport + OnlineSecurity Bundle

Test whether targeted adoption of both services among high-risk Fiber Optic customers improves retention.

A pilot should compare retention outcomes between targeted customers and an appropriate comparison group.

---

# Decision Principle

The analysis supports a shift from:

**Broad retention campaigns**

to:

**Targeted, early and measurable retention interventions.**

The objective is not simply to identify customers who churned.

It is to determine:

> **Where should management act first, which intervention should be tested, and how should its impact be measured?**

---

## Analytical Limitations

The analysis should be interpreted with the following limitations:

- Observed relationships represent **associations, not causality**.
- The dataset does not contain all operational variables that may explain the Fiber Optic customer experience.
- `TotalCharges` is structurally related to customer tenure.
- Recommended interventions should be tested before organisation-wide deployment.
- Segment-level churn rates should not be interpreted as predictive probabilities for individual customers.

---

## Tools

- **Power BI** — Data preparation, KPI development, segmentation, analysis and dashboarding
- **DAX** — Business measures and analytical calculations
- **Python** — Statistical visualisation and complementary analysis
- **Pandas** — Data manipulation and validation
- **Matplotlib** — Box Plot
- **Correlation Analysis** — Numerical relationship exploration

---

## Project Deliverables

This repository contains the analytical deliverables developed for the project:

- **Business Analytics Report**
- **Dataset Inspection Report**
- **Analytical Notebook (.ipynb)**
- **Power BI Dashboard**
- **Final Presentation**
- **Source Dataset**

---

## Repository Structure

```text
customer-churn-retention-analysis/
│
├── README.md
│
├── data/
│   └── WA_Fn-UseC_-Telco-Customer-Churn.csv
│
├── notebook/
│   └── Customer_Churn_Analysis.ipynb
│
├── reports/
│   ├── Business_Analytics_Report.pdf
│   └── Dataset_Inspection_Report.pdf
│
├── presentation/
│   └── Customer_Churn_Analysis_Presentation.pdf
│
├── dashboard/
│   └── Customer_Churn_Analysis.pbix
│
└── images/
    └── dashboard_overview.png
```

---

## Author

**Nancy Lee YIMBERE ALAPINI**

**Performance & Decision Intelligence Analyst**  
*KPI Design, Performance Management & Decision Support | Telecom QoS • Human & Operational Performance*

This project was completed as part of the **AnalystLab Africa Data Analytics Internship Programme**.
