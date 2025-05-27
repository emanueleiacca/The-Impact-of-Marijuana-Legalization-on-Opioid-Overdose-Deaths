# 🌿 Marijuana Legalization and Opioid Mortality: A Causal Analysis Using DiD and IV Models

## 📘 Project Overview

This project explores the potential impact of **recreational marijuana legalization** on **opioid-related mortality** in the United States, using econometric methods such as **Difference-in-Differences (DiD)**, **Instrumental Variables (IV)**, and **Event Studies**.

### ❓ Research Question

> _Can cannabis policy reform help reduce opioid-related harms?_

While earlier studies reported reductions in opioid deaths post-legalization, more recent work has shown mixed results. This study contributes to the debate by applying rigorous causal inference tools to high-quality state-level panel data.

---

## 🧠 Motivation

The opioid crisis continues to devastate U.S. communities. At the same time, many states have reformed their cannabis policies. Understanding whether these changes have a **protective**, **neutral**, or **harmful** effect on opioid outcomes is a pressing public health question — not only for the U.S., but also for **Europe**, where similar crises may emerge.

---

## 🗂️ Dataset

- **Source**: CDC (Centers for Disease Control and Prevention) — Provisional Drug Overdose Death Data
- **Structure**: Monthly panel data from 2016 onward
- **Geographic Scope**: Massachusetts (treatment) vs. New Hampshire (control)
- **Drugs Covered**:
  - Opioids (total, synthetic, heroin, methadone)
  - Cocaine
  - Psychostimulants

Additional covariates:
- Minimum wage, unemployment, GDP
- Arrest data, election results
- COVID-19 dummy
- All variables converted to per-100,000 people

---

## 🔧 Methodology

### 1. **Data Cleaning & Imputation**
- Addressed missing values via **Kalman filtering** and backward fill
- Merged external socioeconomic and political covariates
- Normalized all values per capita

### 2. **Difference-in-Differences (DiD)**
- `treated` = 1 for Massachusetts; 0 for New Hampshire  
- `post` = 1 for months after legalization rollout  
- Main interaction: `treated × post`

### 3. **Event Study**
- Monthly leads and lags used to explore **dynamic effects**
- Binned time periods to address overfitting
- Plots reveal short-lived drop in overdoses post-legalization, coinciding with COVID-19

### 4. **Instrumental Variables (2SLS and 2SRI)**
- Instrument: Indicator for MA after Jan 2018
- Tested for endogeneity bias
- Found no significant treatment effect on opioid deaths; **robust decline in cocaine deaths**

### 5. **Binary Models (Logit/Probit)**
- Created binary outcome `opioids_up`
- Estimated Logit/Probit models and 2-stage IV Logit (2SRI)
- Mixed and unstable results for opioids; stable decline for cocaine

---

## 📈 Key Results

- 📉 **Cocaine deaths** decreased significantly after legalization (DiD and Event Study)
- ⚖️ **Opioid deaths** showed no statistically significant change
- ✅ **Placebo tests** confirm robustness of cocaine finding
- 🧪 **Endogeneity checks** suggest results are not driven by reverse causality

---

## 🌍 Why This Matters for Europe

Although Europe’s overdose rates are currently lower, warning signs are emerging:
- Germany: 1,600+ deaths/year
- Ireland: 300+ deaths/year
- Netherlands: high exposure despite long-standing cannabis tolerance

This project shows how **causal econometric frameworks** can be adapted to evaluate European policy changes before crises escalate.

---

## 💡 Conclusions

- **Legalization is not a silver bullet**, but it may reduce some non-opioid drug harms (e.g., cocaine).
- More targeted studies are needed, especially in Europe.
- Future work should integrate **mental health**, **treatment access**, and **prescription data** to improve inference.
