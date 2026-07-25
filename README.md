# 🏦 Institutional Credit Risk Intelligence & Stress Testing Engine

A production-grade, end-to-end quantitative credit risk and regulatory capital modeling pipeline built in Python, adhering to **Basel III/IV regulatory frameworks** ($PD$, $LGD$, $EAD$, and Expected Loss).

---

## 🚀 Project Architecture

This repository implements a full institutional risk analytics lifecycle across five structured phases:

1. **Data Architecture & Preprocessing:** Cohort isolation, application-time feature selection, monotonic **Weight of Evidence (WoE)** binning, and feature pruning via **Information Value (IV)**.
2. **Probability of Default ($PD$) Scorecard:** Training regulatory **Logistic Regression**, validating coefficient monotonicity, and scaling log-odds to an official **300–850 credit scorecard** via Points-to-Double-Odds (PDO) scaling.
3. **Loss Given Default ($LGD$) Model:** Isolation of defaulted loans, Smithson-Verkuilen boundary transformations, and **Beta Regression** training to model recovery loss rates.
4. **Exposure at Default ($EAD$) & Expected Loss ($EL$):** Credit Conversion Factor ($CCF$) calculations, pipeline integration ($PD \times LGD \times EAD$), and macroeconomic stress-testing.
5. **Production Deployment:** Serving risk models via a **FastAPI** backend and an interactive **Streamlit** risk management dashboard.

---

## 🛠️ Tech Stack & Libraries
* **Languages:** Python 3.10+
* **Data Manipulation & Modeling:** Pandas, NumPy, Scikit-Learn, Statsmodels
* **Backend API:** FastAPI, Uvicorn, Pydantic
* **Frontend UI & Visualization:** Streamlit
* **Deployment & Artifacts:** Joblib

---

## 📂 Repository Structure

```text
credit-risk-engine/
├── notebooks/
│   └── credit_risk_model_training.ipynb   # Original exploratory & training notebook (Colab)
├── models/
│   ├── logistic_scorecard_model.pkl       # Trained PD scorecard artifacts
│   └── beta_lgd_model.pkl                 # Trained LGD beta regression artifacts
├── app.py                                 # FastAPI inference backend
├── dashboard.py                           # Streamlit risk management UI
└── requirements.txt                       # Project dependencies
