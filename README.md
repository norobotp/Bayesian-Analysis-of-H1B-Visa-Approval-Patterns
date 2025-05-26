# 📊 Bayesian Analysis of H1B Visa Approval Patterns (2022–2024)

This project investigates factors influencing the success of H1B visa petitions using a **hierarchical Bayesian model**. It evaluates how employer application volume, industry sector, and geographic location affect approval probabilities for both initial and continuing applications.

## 🔍 Objectives

1. Quantify the relationship between employer application volume and approval rates  
2. Identify industry sectors with high approval consistency  
3. Analyze geographic patterns in visa petition outcomes  
4. Compare trends in **initial vs continuing** applications  
5. Provide **probabilistic insights** for optimizing application strategies

## 🗂️ Data Description

- **Source**: USCIS H-1B Employer Data Hub (2022–2024)
- **Scope**: 102,865 employers
- **Variables**:
  - Approval counts (initial & continuing)
  - Application volume (binned)
  - NAICS industry codes
  - Employer location (state-level)

## 📈 Methodology

- **Model Type**: Hierarchical Bayesian logistic regression
- **Structure**:
  - Top-level: Volume category  
  - Nested levels: Industry and location effects  
  - Separate models for initial and continuing applications  
- **Priors**:
  - Standard normal for fixed effects  
  - Half-normal for variance components  
- **Implementation**: Stan (`rstan`) with 4 chains, 15,000 iterations each

## ✅ Results

- **Volume Effect**: Strong positive correlation between application volume and approval probability  
- **Industry Trends**: Information, Manufacturing, and Finance consistently show high approval rates  
- **Geographic Insights**: States like CA, IL, MI show strong performance, especially at high volumes  
- **Initial vs Continuing**:
  - Initial applications show more variance, especially for small employers  
  - Continuing applications show higher stability in success probability  

## 🎯 Implications

- **For Employers**:
  - Small employers should target strong industries (e.g., Healthcare, Construction)
  - Larger firms benefit from consistent approvals, especially in tech hubs

- **For Job Seekers**:
  - Larger employers (100+ apps) offer predictable outcomes
  - Industry choice (e.g., Information, Finance) and location significantly affect success

## ⚙️ Tools and Packages

- `R`, `rstan`, `bayesplot`, `ggplot2`, `dplyr`
- MCMC diagnostics and posterior predictive checks
- Density overlays, trace plots, and credible intervals

---

## 📎 Output

- Full PDF report: `451_FinalReport (3).pdf`  
- Includes EDA, modeling formulation, diagnostics, visualizations, and discussion

---

## 🧠 Citation & Resources

- USCIS H-1B Employer Data Hub: https://www.uscis.gov/data-reports/h-1b-employer-data-hub  
- Gelman et al. (2013). *Bayesian Data Analysis*  
- Kruschke (2014). *Doing Bayesian Data Analysis*  
- Stan Team: https://mc-stan.org/rstan/

---

*This project was completed as part of a graduate-level Bayesian statistics course at the University of Michigan.*
