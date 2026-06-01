# Hybrid Econometric and Machine Learning

Government Expenditure and Poverty Reduction 

Hybrid-ML-Project

## 🔍 Analysis
[Based on the study: Beyond Averages: A Hybrid Econometric and Machine Learning Approach to Evaluating Government Capital Expenditure and Poverty Reduction in Indonesia]

---

## 🎯 Objective
Evaluating the causal impact of government capital expenditure on poverty reduction across 34 Indonesian provinces by unmasking regional nuances and overcoming the limitations of traditional linear econometric models.

---

## 🛠 Tools
- Double Machine Learning (DML)
- Causal Forests
- Two-Way Fixed Effects (TWFE)
- Random Forests & Lasso (LassoCV)

---

## 📊 Dataset
Strongly balanced panel dataset covering **34 Indonesian provinces over 7 years (N=238)**.
- **Outcome Variable:** Poverty rate (average incidence of 10.94%)
- **Treatment Variable:** Log-transformed government capital expenditure
- **Control Variables:** Human Development Index (HDI), log government spending, unemployment percentage, investment (domestic & foreign), and trade openness.

---

## ⚙️ Data Preparation & Preprocessing
1. **Multicollinearity Check (VIF Test):** Verified no problematic overlap (all scores < 2.54).
2. **Heteroskedasticity Check (Breusch-Pagan Test):** Confirmed variance inconsistency (p < 0.001).
3. **Error Correction:** Applied entity-clustered standard errors to account for the heteroskedasticity.
4. **Confounder Isolation:** Used independent Random Forests to mathematically scrub background noise and isolate leftovers (Double Machine Learning approach).

---

## 🤖 Modelling

**Metric:** Average Treatment Effect (ATE) & Conditional Average Treatment Effect (CATE)

**Model Comparison:**
- **Two-Way Fixed Effects (TWFE):** ATE = -0.158 (Statistically insignificant, p = 0.634)
- **Panel Double Machine Learning (DML):** ATE = -0.254 (Stronger signal, handles messy realities)
- **LassoCV (Alternative Learner):** ATE = -0.403 (Robustness check)
- **Causal Forests:** Mean CATE = -0.337 (Calculates custom scores per province)

---

## 🔧 Results & Heterogeneity (Best Model)

Best Approach : **Causal Forests integrated with DML** yielding :  
- **Overall Mean CATE: -0.337** - **Improvement:** Successfully unmasked significant regional effects hidden by the baseline TWFE model.
- **Highest Poverty Reduction Impact:** Gorontalo (-0.906) and DI Yogyakarta (-0.805)
- **Lowest Poverty Reduction Impact (of top 10):** Bali (-0.434)
- **Robustness Check (Placebo):** Shuffling data resulted in an ATE of -0.015, proving the model wasn't hallucinating.
