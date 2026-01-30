# Identifying Early Signals of Long-Term Subscription  
### A Data-Driven SaaS Churn Risk Analysis

## Overview

This project analyzes early-stage customer behavior in a fictional SaaS platform (RavenStack) to identify signals associated with early churn versus long-term retention.

Rather than focusing on perfect churn prediction, the analysis reframes churn as a prioritization problem:  
**Which customers should receive proactive intervention during onboarding?**

The notebook combines early usage behavior, support friction signals, and interpretable risk scoring to translate customer analytics into operational retention strategy.

---

## Business Framing

Customer churn in subscription businesses is rarely caused by a single catastrophic event.  
It is more often driven by accumulated onboarding friction.

This project asks:

> Can we detect early warning signals within the first 30 days and use them to prioritize retention effort?

The goal is not just analytics —  
it is actionable customer success strategy.

---

## Research Objective

Identify early-stage behavioral signals that distinguish:

- customers who churn within 90 days  
- customers who remain subscribed 180+ days

and translate those signals into an operational risk prioritization framework.

---

## Data Description

The dataset simulates a multi-table SaaS environment including:

- account metadata
- subscription history
- feature usage logs
- support tickets
- churn events

This structure mirrors real-world SaaS analytics pipelines where behavior, billing, and support systems must be integrated.

All analysis focuses on the first **30 days after signup**, the most critical onboarding window.

---

## Analytical Approach

The project follows a layered analytical structure:

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
- engagement persistence

Finding:
Usage volume differences are small and insufficient to explain churn alone.

---

### 3. Early Support Friction Analysis

Support signals examined:

- number of early support tickets
- resolution time
- escalation rate
- satisfaction scores

Finding:
Early churners experience slightly higher friction across all support indicators.

This suggests churn is more closely tied to onboarding experience than raw activity.

---

### 4. High-Risk Segment Identification

Customers are flagged as high-risk when early support friction crosses defined thresholds.

Result:
High-risk customers exhibit ~1.6× higher early churn probability.

These customers are not guaranteed churners —  
they represent high-leverage intervention targets.

---

### 5. Interpretable Risk Score Construction

A weighted risk score aggregates:

- support ticket volume
- escalation signals
- resolution delays
- engagement persistence

The score functions as a ranking tool, not a binary predictor.

It enables prioritized retention effort.

---

## Key Insights

Early churn is not driven by low activity alone.

It is more strongly associated with onboarding friction and support severity.

This shifts retention strategy from engagement nudges to friction reduction.

Risk signals are probabilistic, not deterministic —  
but consistent enough to guide resource allocation.

---

## Insight → Action Translation

This analysis supports a proactive onboarding defense strategy:

- Flag accounts with repeated early support escalation
- Trigger priority onboarding workflows
- Assign targeted customer success outreach
- Measure retention lift post-intervention

The objective is smarter prioritization, not blanket intervention.

Retention effort should follow risk ranking.

---

## Business Implication

The project reframes churn analytics as a resource allocation problem.

Instead of asking:

> Who will churn?

It asks:

> Where will intervention have the highest marginal impact?

This perspective aligns analytics with operational decision-making.

---

## Limitations

- Synthetic dataset (simulated SaaS environment)
- Limited long-term financial metrics
- Simplified support severity modeling

The framework demonstrates methodology rather than production forecasting.

---

## Conclusion

Early churn emerges from accumulated onboarding friction, not isolated events.

Support signals provide actionable early warning indicators.

An interpretable risk score enables targeted retention strategy without overfitting.

The result is a scalable framework for data-informed customer success prioritization.

---

## Tools & Techniques

- Python (Pandas, NumPy, Matplotlib)
- Behavioral feature engineering
- Early-window cohort analysis
- Risk scoring framework
- Exploratory data visualization

---

## Author

Jihoo Lee  
Data Analytics & Business Analytics Portfolio Project
