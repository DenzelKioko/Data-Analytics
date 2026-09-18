# 📊 Data Analytics — Regression Analysis Portfolio

A collection of statistical analyses written in **R** demonstrating three core regression techniques; simple linear regression, multiple linear regression, and logistic regression — applied to synthetic business datasets. Each analysis follows a full statistical workflow: exploratory data analysis (EDA), model fitting, diagnostic testing of regression assumptions, and business-oriented interpretation of results.

---

## 📁 Contents

| Analysis | File | Business Question |
|---|---|---|
| **Simple Linear Regression** | `simple_linear_regression.Rmd` | Does purchase frequency predict Customer Lifetime Value (CLV)? |
| **Multiple Linear Regression** | `multiple_linear_regression.Rmd` | Do YouTube, TikTok, and Facebook ad spend predict Sales? |
| **Logistic Regression** | `logistic_regression.Rmd` | Do monthly fee, customer age, and support calls predict subscription renewal? |

---

## 🔍 Methodology (applied consistently across all three analyses)

1. **Load the Dataset** — import and inspect structure/dimensions
2. **Initial EDA**
   - Measures of frequency, central tendency, and distribution (variance, SD, kurtosis, skewness)
   - Measures of relationship (covariance, correlation)
   - Visualizations: histograms, box plots, missing-data maps, correlation plots, scatter plots
3. **Statistical Test** — fit the regression model and interpret coefficients, confidence intervals, and model fit metrics
4. **Diagnostic EDA** — validate regression assumptions:
   - Linearity
   - Independence of errors (Durbin-Watson test for autocorrelation)
   - Normality (Q-Q plots)
   - Homoscedasticity (scale-location plots, Breusch-Pagan test)
   - Multicollinearity (VIF)
   - Outlier/influence detection (Cook's distance, influence plots) — logistic regression only
5. **Interpretation of Results**
   - Academic statement (formal statistical reporting, APA-style)
   - Business analysis (practical implications and recommendations)
   - Limitations

---

## 📈 Key Findings

**Simple Linear Regression — CLV vs. Purchase Frequency** (N = 500)
Purchase frequency is a strong, statistically significant predictor of CLV (R² = 0.964). Each additional purchase increases CLV by ~19.5 units on average.

**Multiple Linear Regression — Sales vs. Ad Spend** (N = 10)
The combined model explains 97.3% of variance in Sales, but no individual channel (YouTube, TikTok, Facebook) is statistically significant on its own — likely due to a small sample size and high multicollinearity between spend across channels (VIF > 47 for all predictors).

**Logistic Regression — Subscription Renewal** (N = 1,000)
Support calls has the strongest effect: each additional call roughly doubles the odds of renewal (OR = 2.01). Higher monthly fees decrease renewal odds, while older customers are more likely to renew. Model AUC = 0.717 (acceptable discrimination).

---

## 🛠️ Tech Stack

- **Language:** R
- **Report format:** R Markdown (`.Rmd`), knitted to PDF
- **Key packages:**
  - `pacman` — package management
  - `readr`, `dplyr` — data import/wrangling
  - `e1071` — kurtosis/skewness
  - `ggplot2`, `ggcorrplot`, `corrplot`, `Amelia` — visualization
  - `car` — VIF, component-residual plots, influence plots
  - `lmtest` — Durbin-Watson & Breusch-Pagan tests
  - `gvlma` — global validation of linear model assumptions
  - `pROC` — ROC/AUC for logistic regression

---

## 🚀 Reproducing the Analyses

### Prerequisites
- R (4.x recommended)
- RStudio (recommended for knitting `.Rmd` files)

### Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/DenzelKioko/data-analytics.git
   cd data-analytics
   ```

2. **Open an `.Rmd` file in RStudio** and knit it — required packages install automatically via `pacman::p_load()`.

3. **Data files** — each analysis expects its dataset in a `data/` subfolder:
   ```
   data/
   ├── clv_data.csv
   ├── advertising.csv
   └── subscription_churn.csv
   ```
