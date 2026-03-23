# Early Churn Signal Analysis in a SaaS Product

## Overview
This project analyzes early customer behavior in a fictional multi-table SaaS dataset (RavenStack) to identify which signals are associated with **churn within 90 days** versus **long-term subscription**.

The analysis found that basic early usage metrics showed only small differences across customer groups, while **early support friction** was more useful for identifying at-risk accounts. Accounts flagged for early support friction showed an early churn rate about **1.6x higher** than the rest of the population.

## Business Question
Which customer behaviors in the first 30 days are most associated with **early churn** versus **long-term retention** in a subscription SaaS product?

## Key Findings
- Basic early usage metrics showed only **modest differences** between early churners and long-term subscribers.
- Early support friction provided more useful signals than raw usage volume alone.
- Accounts flagged as high-risk based on early support friction showed an **early churn rate about 1.6x higher** than the rest of the population.
- A simple weighted risk score helped rank accounts for **retention prioritization**, rather than serving as a deterministic churn model.

## Dataset
This project uses a fictional multi-table SaaS dataset with five tables:

- `accounts`
- `subscriptions`
- `feature_usage`
- `support_tickets`
- `churn_events`

The dataset was designed to simulate common SaaS lifecycle signals, including onboarding behavior, subscription history, support interactions, and churn outcomes.

## Customer Outcome Definition
To create a cleaner comparison, accounts were grouped by subscription duration:

- **Early Churn**: subscription ended within 90 days  
- **Long-Term**: subscription lasted 180 days or longer  
- **Mid-Term**: 91–179 days, excluded from the primary comparison  

## Early Observation Window
Early behavior was measured within the first 30 days after signup to capture onboarding-period engagement before longer-term retention outcomes were fully realized.

## Analytical Approach

### 1. Measure early usage behavior
I first evaluated onboarding-period usage behavior, including:

- total usage events
- number of unique features used
- beta feature adoption
- number of active days in the first 30 days

These usage-based metrics showed only modest differences between early churners and long-term subscribers, suggesting that raw activity volume alone was not enough to clearly separate the two groups.

### 2. Measure early support friction
I then examined support interactions during the first 30 days after signup, including:

- number of support tickets
- average resolution time
- escalation rate
- average satisfaction score

Compared with usage-based metrics, support-related signals showed more consistent directional differences. Early churners had slightly longer resolution times and slightly higher escalation rates, suggesting that onboarding friction may be more informative than raw usage volume alone.

## High-Risk Segment Validation
To translate the findings into an operational rule, I defined a simple **high-risk flag** for accounts with repeated early support demand or any escalation during the first 30 days.

Accounts flagged as high-risk showed an early churn rate about **1.6x higher** than the rest of the population. This does not make support friction a deterministic predictor of churn, but it does make it a useful signal for prioritizing intervention.

## Interpretable Risk Scoring
To move from descriptive analysis to prioritization, I built a simple weighted risk score using:

- early support ticket volume
- escalation rate
- average resolution time
- early engagement persistence

The score is intended as a **prioritization tool**, not a production prediction model. Customers in the top risk percentiles showed higher early churn rates than the broader population, supporting its use for ranked retention outreach.

## Business Takeaway
This project suggests that early churn is better framed as a **prioritization problem** than a pure prediction problem.

In this dataset, basic usage volume alone had limited explanatory value, while early support friction provided a more practical signal for identifying accounts that may need proactive onboarding support.

## Tools
Python, Pandas, NumPy, Matplotlib, Jupyter Notebook
