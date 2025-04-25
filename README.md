# Predicting Bank Loan Interest Rates: A Regression-Based Approach

## Project Overview

This project explores how borrower characteristics influence interest rates on bank loans using multiple linear regression modeling. The analysis is based on a publicly available dataset sourced from Kaggle. The aim is to help financial institutions improve their loan approval processes and risk assessments by identifying the most predictive features for interest rate determination.

## Objectives

- Identify the relationship between loan characteristics and interest rates
- Clean and prepare the dataset for modeling
- Build a regression model and validate assumptions
- Interpret coefficients to gain actionable financial insights

## Dataset

**Source**:  
* Loan Data for Dummy Bank (Kaggle)

**Key Variables Used**:

* interest_rate (target)
* loan_amount, annual_inc, emp_length_int, dti (quantitative)
* income_category, term, purpose, home_ownership, grade, interest_payments (categorical)

## Data Preparation

- Removed missing values and duplicates
- Standardized categorical values
- Filtered outliers in interest rates
- Verified consistency and quality using duplicated() and unique() methods

## Modeling Approach

- **Full Model**: All variables included; Adjusted R² = 0.963, RSE = 0.6711
- **Stepwise Regression**: 6 variables retained; similar R² but slightly higher RSE
- **Interaction Model**: Overfit; minor R² gain but reduced interpretability
- **Final Selection**: Full model chosen due to best balance between performance and simplicity

## Assumption Checks

✅ Linearity: Residual vs fitted plot showed no patterns  
✅ Normality: Histogram & QQ-plot confirm symmetrical residuals  
✅ Independence: Residuals randomly scattered  
⚠️ Homoscedasticity: Breusch-Pagan test indicated mild heteroscedasticity, but negligible impact due to large dataset  
✅ Multicollinearity: All GVIF values < 10, no strong collinearity detected  

## Final Model Insights

**Most impactful predictors:**

- grade: higher grade → higher interest rate (e.g., G adds +12.37%)
- interest_payments: low payment associated with higher rate
- purpose: educational → large increase in interest rate
- Less impactful predictors: loan_amount, annual_inc, dti (coefficients near 0)

## Tasks Performed:

- Data cleaning, preprocessing, and feature engineering in Pytho
- Model building using multiple regression and assumption validation
- Result interpretation and model selection

## Future Work

- Test nonlinear models (e.g., Random Forest, Gradient Boosting)
- Incorporate credit history or time series features if available
- Investigate interaction effects further

## References

* Federal Reserve. (2020). How banks decide whether to lend to you
* Hayes, A. (2024). Multicollinearity explained. Investopedia
* Medium, Kaggle, and various academic sources for modeling guidance

## Conclusion

This project demonstrates that multiple regression can accurately predict interest rates based on a set of borrower attributes. While traditional regression works well in this setting, future models may benefit from incorporating non-linearities or alternative ML algorithms. The project not only supports financial decision-making but also highlights the importance of model validation and transparent communication of results.

