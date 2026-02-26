# Retail Credit Portfolio Risk Assessment and Stress Testing

## Overview

This project develops a quantitative credit risk framework for a retail loan portfolio using Probability of Default (PD) modeling, Monte Carlo loss simulation, and stress testing techniques.

The objective is to construct a portfolio-level risk engine capable of estimating:

- Expected Loss (EL)
- Value-at-Risk (VaR)
- Conditional Value-at-Risk (CVaR)
- Capital sensitivity under stressed economic conditions

The framework reflects practical methodologies used within banking Risk Functions.

---

## Credit Risk Framework

The portfolio loss formulation follows standard credit risk methodology:

Expected Loss (EL) = PD × LGD × EAD

Where:

- PD (Probability of Default) — estimated using logistic regression  
- LGD (Loss Given Default) — assumed 50% (base), 65% (stress)  
- EAD (Exposure at Default) — loan amount  

---

## Dataset

The analysis uses a retail lending dataset containing:

- Borrower demographics
- Income and employment information
- Loan characteristics (amount, interest rate, grade)
- Historical default indicator

Data preprocessing included:

- Removal of unrealistic outliers
- Economically consistent missing value imputation
- Final portfolio size: 31,677 loans

---

## Exploratory Risk Profiling

Key findings:

- Overall default rate: 21.55%
- Default rates increase monotonically from Grade A to G
- Lower-income borrowers exhibit significantly higher default rates

These patterns confirm economic consistency and suitability for PD modeling.

---

## Probability of Default (PD) Modeling

A logistic regression model was trained to estimate borrower-level PD.

Model performance:

- ROC–AUC: 0.864
- Strong discriminatory power
- Economically coherent risk signals

The model produces individual default probabilities for portfolio aggregation.

---

## Portfolio Risk Results

### Base Scenario (Independent Defaults)

- Expected Loss: ~11.29M  
- VaR (95%): ~11.60M  
- CVaR (95%): ~11.67M  

Loss distribution aligns with analytical expected loss under normal conditions.

---

## Stress Testing Scenario

Stress assumptions:

- PD increased by 30%
- LGD increased from 50% to 65%

Stressed results:

- VaR (95%): ~18.60M  
- CVaR (95%): ~18.70M  

Tail risk increases by approximately 60%, demonstrating significant sensitivity to macroeconomic deterioration.

---

## Risk Interpretation

This framework demonstrates:

- Transition from borrower-level modeling to portfolio-level aggregation
- Tail risk measurement using Monte Carlo simulation
- Capital impact estimation under stressed scenarios
- Sensitivity of portfolio losses to economic shocks

The analysis reflects core methodologies applied in Credit Risk and Portfolio Risk Management functions.

---

## Tools & Methods

- Python
- Pandas
- NumPy
- Scikit-learn
- Logistic Regression
- Monte Carlo Simulation
- VaR & CVaR Estimation

---

## Future Extensions

- Correlated default modeling using a systematic risk factor
- PD calibration assessment
- Capital allocation by segment
- Concentration risk analysis
