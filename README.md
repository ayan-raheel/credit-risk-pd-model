# Credit Risk PD Modeling (Logistic Regression + XGBoost)

This project builds a **Probability of Default (PD)** model for loan applicants and converts model outputs into **business-ready risk insights** such as risk buckets, observed default rates by segment, and decision support for credit approvals, pricing, and collections.

---

## Business Problem
Financial institutions need to quantify credit risk at the individual borrower level. This is done to ensure the financial insitution mitigates credit risk.  
The goal of this project is to estimate **Probability of Default (PD)** and translate model outputs into actionable credit decisions.

---

## Dataset
This project uses a **publicly available credit risk dataset** commonly used for learning and benchmarking.  
The dataset itself is **not included** in this repository.

---

## Approach
- Define X and y variables (loan_status)
- Use a 40% Test Split and 60% Train Split
- Separate numerical and categorical features
- Preprocess data using `ColumnTransformer` and `Pipeline`
- Train a **Logistic Regression** model as a transparent baseline
- Train an **XGBoost** model to capture non-linear risk patterns
- Evaluate models using **ROC-AUC**, **confusion matrices**, and train vs test performance
- Convert predicted probabilities into **risk buckets** for business interpretation

---

## Key Results

### Portfolio Distribution by PD Bucket
- **Very Low:** 40.1%
- **Low:** 20.3%
- **Medium:** 14.5%
- **High:** 25.1%

### Observed Default Rate by PD Bucket
- **Very Low:** 1.77%
- **Low:** 6.05%
- **Medium:** 13.13%
- **High:** 71.02%

> Defaults increase monotonically across buckets, indicating strong risk separation and a business-usable PD model.

---

## Business Insights
- **Credit Policy:** Restrict or apply tighter controls for the highest-risk bucket
- **Pricing:** Apply risk-based pricing across PD segments
- **Collections:** Prioritize early intervention for high-PD borrowers

---

## Repository Structure
- `notebooks/credit_risk_pd_model.ipynb` — end-to-end modeling and analysis
- `data/data_source.md` — dataset source and notes (dataset not included)
- `requirements.txt` — Python dependencies

---

## How to Run
```bash
pip install -r requirements.txt
jupyter notebook notebooks/credit_risk_pd_model.ipynb
