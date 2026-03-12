# Insurance Portfolio Review Prioritisation

SQL analysis of a large insurance portfolio to identify which policies and segments generate the most claim workload.

---

## Business Problem
Insurance review teams need to investigate policies generating high claim activity.  
With a large portfolio, manual review does not clearly show where most claim workload is coming from.

This project builds a repeatable SQL workflow to identify where review effort should be prioritised.

---

## Dataset
Public insurance portfolio dataset used for workflow demonstration.

- ~1.05M policy records  
- 20+ fields including policy type, property type, location, premium amount, duration, and claim count

---

## Data Preparation (Python)
Data was cleaned before SQL analysis.

Steps included:
- Removing duplicate policy IDs
- Checking invalid values in claims, premium and duration
- Creating analytical groupings:
  - `claim_band` → 0, 1, 2, 3+
  - `tenure_band` → 0–1, 2–3, 4–5, 6+

Notebook: `insurance_dataset_cleaning.ipynb`

---

## SQL Analysis
Main SQL workflow: `insurance_portfolio_analysis.sql`

Key steps:

1. Build canonical **policy-level dataset**
2. Calculate **portfolio baseline metrics**
3. Compare **Policy_Type × Location segments**
4. Rank segments by **claim contribution**
5. Test **segment-level concentration**
6. Perform **policy-level decile analysis**
7. Compare **tenure cohorts**
8. Check **segment stability and dispersion**

---

## Key Result
Segment-level analysis showed balanced behaviour across portfolio segments.

However, **policy-level concentration exists**:

Top **30% of policies generate ~55% of total claims**.

This allows review teams to prioritise investigation on a smaller subset of policies.

---

## Tools
SQL  
Python  
Tableau
