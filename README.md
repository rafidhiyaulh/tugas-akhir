# Analisis dan Evaluasi Prediksi Harian PM₁₀ Jakarta Menggunakan Model Hibrida Random Forest Regresi-ARIMA Berbasis Rekayasa Fitur

**Muhammad Rafi Dhiyaulhaq — 18222069**  
Program Studi Sistem dan Teknologi Informasi, Sekolah Teknik Elektro dan Informatika  
Institut Teknologi Bandung

---

## Overview

Undergraduate thesis (*Tugas Akhir*) proposing a sequential hybrid Random Forest–ARIMA architecture with time-series feature engineering to improve daily PM₁₀ forecasting accuracy for DKI Jakarta (2010–2025). The model is augmented with SHAP-based explainability to identify key pollution drivers and support air quality policy decisions.

This thesis is conducted as part of a lecturer research project under the supervision of **Dr. Fetty Fitriyanti Lubis, S.T., M.T.**

**Grade: A**

---

## Publication

Accepted to the **2026 IEEE International Conference on Future Machine Learning and Data Science (FMLDS 2026)**.

---

## Results

| Model | RMSE |
|---|---|
| **Hybrid RF–ARIMA (proposed)** | **13.4004** |
| Random Forest Regression | 13.5717 |
| XGBoost | 14.3307 |
| ARIMA | 18.8432 |

Evaluated with 5-fold time-series cross-validation.

---

## Repository Structure

```
.
├── TA.tex                                          # Main LaTeX entry point
├── daftar-pustaka.bib                              # Bibliography (BibLaTeX)
├── Bab I - Pendahuluan.tex                         # Chapter I  — Introduction
├── Bab II - Studi.tex                              # Chapter II — Literature Review
├── Bab III - Analisis.tex                          # Chapter III — Analysis
├── Bab IV - Perancangan.tex                        # Chapter IV — Design
├── Bab V - Implementasi.tex                        # Chapter V  — Implementation
├── Bab VI - Evaluasi.tex                           # Chapter VI — Evaluation
├── Bab VII - Penutup.tex                           # Chapter VII — Conclusion
├── 5 Abstrak.tex                                   # Abstract
├── Lampiran-A.tex                                  # Appendix A
├── images/                                         # Figures and diagrams
├── tables/                                         # Tables
├── listings/                                       # Code listings
├── algorithms/                                     # Algorithm pseudocode
├── 18222069_Muhammad Rafi Dhiyaulhaq.pdf           # Final signed thesis report
├── 18222069_Muhammad Rafi Dhiyaulhaq_Paper.pdf     # IEEE FMLDS 2026 paper
└── 18222069_Muhammad Rafi Dhiyaulhaq_Poster.png    # IEEE FMLDS 2026 poster
```

> Note: front/back-matter files (title page, approval sheet, originality statement, AI-usage
> statement, preface, and the various *Daftar* lists) are administrative documents kept locally
> but excluded from version control via `.gitignore`.

---

## Documents

**`18222069_Muhammad Rafi Dhiyaulhaq.pdf`**  
Complete, signed, and approved undergraduate thesis (laporan lengkap).

**`18222069_Muhammad Rafi Dhiyaulhaq_Paper.pdf`**  
Conference paper accepted at the 2026 IEEE International Conference on Future Machine Learning and Data Science (FMLDS 2026).

**`18222069_Muhammad Rafi Dhiyaulhaq_Poster.png`**  
Conference poster accepted at the 2026 IEEE International Conference on Future Machine Learning and Data Science (FMLDS 2026).

---

## Compilation

Requires XeLaTeX and Biber.

```bash
xelatex TA.tex
biber TA
xelatex TA.tex
xelatex TA.tex
```

---

<p align="center"><sub>© 2026 Muhammad Rafi Dhiyaulhaq · Institut Teknologi Bandung</sub></p>
