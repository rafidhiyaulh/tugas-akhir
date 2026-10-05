# Analisis dan Evaluasi Prediksi Harian PM₁₀ Jakarta Menggunakan Model Hibrida Random Forest Regresi-ARIMA Berbasis Rekayasa Fitur

**Muhammad Rafi Dhiyaulhaq**  
Program Studi Sistem dan Teknologi Informasi, Sekolah Teknik Elektro dan Informatika  
Institut Teknologi Bandung

---

## Overview

Undergraduate thesis (*Tugas Akhir*) that analyzes and evaluates a sequential hybrid Random Forest–ARIMA architecture with time-series feature engineering for next-day (t+1) PM₁₀ forecasting in DKI Jakarta (2010–2025). The model is complemented with TreeSHAP explainability to identify the main drivers of the forecasts.

This thesis was conducted as part of a lecturer research project under the supervision of **Dr. Fetty Fitriyanti Lubis, S.T., M.T.**

**Grade: A**

---

## Publication

*Analysis and Evaluation of Daily PM₁₀ Forecasting in Jakarta Using a Hybrid Random Forest Regressive and ARIMA Model Based on Feature Engineering.*  
M. R. Dhiyaulhaq, F. F. Lubis, and J. Sembiring.  
Accepted to the **2026 IEEE International Conference on Future Machine Learning and Data Science (FMLDS 2026)**, Kobe, Japan, 20–23 November 2026.

---

## Results (IEEE FMLDS 2026 paper)

Next-day forecasting on a chronological hold-out test set of 1,043 days (Oct 2021 – Feb 2025). Values are PM₁₀ ISPU sub-indices.

| Model | RMSE | MAE | R² |
|---|---|---|---|
| **Hybrid RF–ARIMA (proposed)** | **14.73** | **10.34** | **0.37** |
| Random Forest (Optuna-tuned) | 14.82 | 10.55 | 0.36 |
| ARIMA(5,1,0), rolling one-step | 15.23 | 10.70 | 0.32 |
| XGBoost (untuned) | 16.52 | 12.09 | 0.20 |
| Persistence (yₜ = yₜ₋₁) | 17.75 | 11.96 | 0.08 |

**Key findings**
- The hybrid reduces RMSE by 17.0% vs. persistence and 3.3% vs. a rolling ARIMA. Both differences are significant under the Diebold–Mariano test.
- The ARIMA residual stage improves on the tuned Random Forest by only 0.63% RMSE, which is not significant (p = 0.17). Most of the skill comes from PM₁₀ lag and rolling features.
- TreeSHAP shows that recent PM₁₀ levels (3-day and 7-day means, 1-day lag) and the dry season dominate the forecasts.

**Setup:** 5,538 daily ISPU records (Jan 2010 – Feb 2025) with 18 features, all built from information available up to day t−1. Missing values are imputed from past data only. Random Forest hyperparameters are tuned with Optuna (TPE) using 5-fold `TimeSeriesSplit` on the training period only. ARIMA is fitted to out-of-bag residuals and applied as a rolling one-step correction.

> **Note:** The paper uses a revised, leakage-free evaluation pipeline. Its results supersede the evaluation figures in the thesis report.

---

## Repository Structure

```
.
├── notebook/
│   └── PM10_Forecasting.ipynb      # Pipeline that reproduces all paper results
├── latex/                                    # Thesis LaTeX source
├── Muhammad Rafi Dhiyaulhaq.pdf              # Final signed thesis report
└── Muhammad Rafi Dhiyaulhaq_Paper.pdf        # IEEE FMLDS 2026 paper
```

## Reproducing the Results

Dataset: daily ISPU records for DKI Jakarta 2010–2025 (Kaggle, *Air Quality Index in Jakarta*).

```bash
pip install pandas numpy scikit-learn statsmodels xgboost optuna shap matplotlib seaborn

jupyter notebook notebook/PM10_Forecasting_corrected.ipynb
```

---

## Compiling the Thesis

Requires XeLaTeX and Biber.

```bash
cd latex
xelatex TA.tex
biber TA
xelatex TA.tex
xelatex TA.tex
```

---

<p