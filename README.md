# Identifying Early Signals of Long-Term Subscription  
## A Data-Driven SaaS Churn Risk Analysis  

---

## Key Results

- Identified that early support friction is a stronger churn signal than usage volume  
- High-risk accounts showed ~1.6× higher early churn probability  
- Developed an interpretable risk scoring framework to prioritize retention intervention  

---

## Overview

This project analyzes early-stage customer behavior in a simulated SaaS platform (RavenStack) to identify signals associated with early churn versus long-term retention.

Rather than focusing on churn prediction, the analysis reframes churn as a prioritization problem:

**Which customers should receive proactive intervention during onboarding?**

The project combines behavioral data and support friction signals to build an interpretable risk-scoring framework for retention prioritization.

---

## Business Framing

Customer churn in subscription businesses is rarely caused by a single event.  
It is more often driven by accumulated onboarding friction.

This project asks:

**Can we detect early signals within the first 30 days and prioritize retention effort accordingly?**

---

## Research Objective

Identify early-stage signals that distinguish:

- Customers who churn within 90 days  
- Customers who remain subscribed 180+ days  

and translate these signals into a risk-based prioritization framework.

---

## Data Description

The dataset simulates a multi-table SaaS environment including:

- account metadata  
- subscription history  
- feature usage logs  
- support tickets  
- churn events  

This structure mirrors real-world SaaS analytics pipelines where behavioral, billing, and support systems must be integrated.

All analysis focuses on the first 30 days after signup — the most critical onboarding window.

---

## Analytical Approach

### 1. Outcome Segmentation

Customers are categorized into:

- Early Churn (≤ 90 days)  
- Long-Term (≥ 180 days)  
- Mid-Term (excluded from primary comparison)  

This creates a clear retention contrast.

---

### 2. Early Usage Analysis

Metrics examined:

- total usage events  
- unique features used  
- active usage days  

**Finding:** Usage differences were minimal and insufficient to explain churn.

---

### 3. Early Support Friction Analysis

Support signals examined:

- number of early support tickets  
- resolution time  
- escalation rate  
- satisfaction scores  

**Finding:** Early churners consistently experienced higher support friction across all indicators.

This suggests churn is more closely tied to onboarding experience than raw activity.

---

### 4. High-Risk Segment Identification

Customers are flagged as high-risk when early support friction crosses defined thresholds.

**Result:** High-risk customers show ~1.6× higher early churn probability.

These users are not guaranteed churners — they represent high-leverage intervention targets.

---

### 5. Interpretable Risk Score Construction

A weighted risk score aggregates:

- support ticket volume  
- escalation signals  
- resolution delays  
- engagement persistence  

The score is designed as a **ranking tool**, not a binary predictor.

It enables prioritization of retention effort based on relative risk.

---

## Key Insights

- Early churn is not driven by low activity alone  
- Onboarding friction and support severity are stronger signals of churn risk  
- Risk signals are probabilistic, but consistent enough to guide prioritization  

This shifts retention strategy from engagement nudges to friction reduction.

---

## Insight → Action

This analysis supports a targeted onboarding strategy:

- Flag accounts with repeated early support escalation  
- Trigger priority onboarding workflows  
- Assign targeted customer success outreach  

The goal is to allocate retention resources where they have the highest impact.

---

## Business Implication

This project reframes churn analytics as a **resource allocation problem**:

**Where will intervention have the highest marginal impact?**

This perspective aligns analytics directly with operational decision-making.

---

## Limitations

- Synthetic dataset (simulated SaaS environment)  
- Limited long-term financial metrics  
- Simplified support severity modeling  

This project demonstrates methodology rather than production forecasting.

---

## Conclusion

Early churn is driven more by accumulated onboarding friction than low activity.

Support signals provide actionable early indicators of churn risk.

An interpretable risk score enables targeted intervention and more efficient allocation of retention resources.

This project demonstrates how analytics can directly inform customer success strategy.

---

## Tools & Techniques

- Python (Pandas, NumPy, Matplotlib)  
- Behavioral feature engineering  
- Early-window cohort analysis  
- Risk scoring framework  
- Exploratory data analysis  

---

## Author

**Jihoo Lee**  
Data Analytics & Business Analytics Portfolio Project
