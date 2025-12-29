# Early Churn Signal Analysis in a SaaS Platform

## Overview
This project analyzes early-stage customer behavior in a fictional multi-table SaaS dataset (RavenStack) to identify signals associated with early churn versus long-term retention.

Rather than focusing on black-box churn prediction, the analysis emphasizes **interpretable early signals** and translates them into a **practical risk prioritization framework** that can support real-world retention decisions.


## Business Question
**Can early customer behavior and experience (within the first 30 days) help identify customers at higher risk of early churn, and how can those signals be operationalized for targeted intervention?**


## Dataset
The analysis uses a synthetic but realistic SaaS dataset consisting of five relational tables:

- **accounts**: customer metadata and signup information  
- **subscriptions**: subscription lifecycle and plan details  
- **feature_usage**: product usage events  
- **support_tickets**: customer support interactions  
- **churn_events**: churn outcomes and reasons  

All tables are linked via `account_id` and `subscription_id`.


## Methodology

### 1. Defining Customer Outcomes
Customers were segmented based on subscription duration:
- **Early Churn**: churned within 90 days  
- **Long-Term**: retained for 180 days or longer  
- **Mid-Term**: intermediate cases (used as reference only)

This outcome-based segmentation enables a clear comparison between early disengagement and sustained retention.


### 2. Early Usage Analysis (Q1)
Early behavior was defined as activity occurring within the first **30 days after signup**.

Initial hypotheses tested whether early usage volume and feature exploration explained churn outcomes, using metrics such as:
- total usage events  
- number of unique features used  
- beta feature adoption  

**Finding:**  
Early usage metrics showed only marginal differences between early churners and long-term subscribers, suggesting that usage volume alone provides limited explanatory power.


### 3. Early Support Friction Analysis (Q2)
Given the limited signal from usage metrics, the analysis shifted to early customer experience indicators derived from support interactions:
- number of early support tickets  
- escalation rate  
- average resolution time  
- satisfaction scores  

**Finding:**  
Early churners consistently exhibited higher support friction, including longer resolution times and higher escalation rates.  
Although differences were moderate in magnitude, their directional consistency indicated that early friction is a more actionable churn signal than usage intensity alone.


### 4. Risk Scoring Framework (Q3)
To operationalize these findings, an interpretable **early churn risk score** was constructed using:
- early support ticket frequency  
- escalation occurrence  
- resolution time  
- early usage persistence (as a protective factor)

Scores were interpreted **relatively** using percentile rankings rather than absolute thresholds.

**Finding:**  
Customers in the top 20% of risk scores showed a meaningfully higher early churn rate (~22% relative increase), validating the framework as a prioritization tool.


## Key Insights
- Early churn is **not strongly driven by usage volume**, but by **early customer friction**
- Support-related signals provide more actionable insight than engagement metrics alone
- Risk scoring is most effective as a **relative ranking mechanism**, not a deterministic predictor
- Targeted intervention strategies can be more efficient than uniform retention efforts


## Business Implications
Rather than attempting to predict churn perfectly, companies can:
- identify high-risk customers early
- trigger proactive support outreach during onboarding
- allocate retention resources more efficiently

This approach improves retention leverage while minimizing unnecessary operational costs.


## Tools & Skills
- Python (pandas, numpy, matplotlib)
- Multi-table data modeling
- Exploratory data analysis (EDA)
- Customer segmentation
- Risk scoring & prioritization
- Business-oriented data storytelling


## Notes
This project uses a fully synthetic dataset and is intended for educational and portfolio purposes.
