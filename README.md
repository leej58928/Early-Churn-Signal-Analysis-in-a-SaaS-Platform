# Early Churn Signal Analysis in a SaaS Product

## Key Results

- High-risk accounts (top 20%) show **~1.6× higher early churn**
- Early support friction signals (tickets, escalations, resolution time) outperform raw usage metrics in identifying churn risk
- Usage volume alone shows **weak separation** between churned and retained users

<img width="1475" height="748" alt="image" src="https://github.com/user-attachments/assets/cae59909-1699-47b0-b2c9-3dcc4c365547" />

Accounts in the top 20% of the risk score distribution exhibit a clearly higher early churn rate, validating the use of early support signals for prioritizing retention outreach.

---

## Business Question

Which customer behaviors in the first 30 days are most associated with early churn versus long-term retention in a subscription SaaS product?

---

## What Actually Matters

Not all early behavior signals are equally useful.

- **Usage metrics** (events, features, activity days) showed limited separation between churned and retained users  
- **Support-related signals** (ticket volume, escalation rate, resolution time) showed more consistent differences  
- This indicates that **onboarding friction is more predictive than engagement volume alone**

---

## Approach

The analysis compares early behavior across churned vs retained accounts using two signal groups:

### 1. Usage Behavior
- total usage events  
- number of unique features used  
- beta feature adoption  
- number of active days (first 30 days)

### 2. Support Friction
- number of support tickets  
- average resolution time  
- escalation rate  
- average satisfaction score  

The goal is to determine which signal group better differentiates early churn risk.

---

## High-Risk Segment Definition

To operationalize the findings, a simple high-risk rule was defined:

- accounts with repeated early support demand  
- or any escalation within the first 30 days  

Accounts flagged as high-risk show **~1.6× higher early churn**, making this a practical signal for early intervention.

---

## Risk Scoring Framework

A simple weighted risk score was constructed using:

- support ticket volume  
- escalation rate  
- resolution time  
- early engagement persistence  

The score is designed for **prioritization, not prediction**.

Accounts in higher risk percentiles consistently show elevated churn rates, supporting its use for ranking accounts for proactive retention outreach.

---

## Business Takeaway

Early churn is better approached as a **prioritization problem rather than a pure prediction problem**.

Instead of relying on overall usage volume, teams can use early support signals to:

- identify at-risk accounts during onboarding  
- prioritize retention outreach  
- reduce churn through earlier intervention  

---

## Dataset

This project uses a fictional multi-table SaaS dataset (RavenStack) with five tables:

- `accounts`  
- `subscriptions`  
- `feature_usage`  
- `support_tickets`  
- `churn_events`  

The dataset simulates common SaaS lifecycle signals, including onboarding behavior, subscription history, support interactions, and churn outcomes.

---

## Customer Outcome Definition

To create a clear comparison:

- **Early Churn**: subscription ended within 90 days  
- **Long-Term**: subscription lasted 180 days or longer  
- **Mid-Term (91–179 days)**: excluded from primary comparison  

---

## Early Observation Window

Early behavior is measured within the first 30 days after signup to capture onboarding-period signals before long-term retention outcomes are realized.

---

## Tools

- Python  
- Pandas  
- NumPy  
- Matplotlib  
- Jupyter Notebook  
