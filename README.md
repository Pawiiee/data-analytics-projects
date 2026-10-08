# 🎬 Movie Revenue & Correlation Analysis

![Python](https://img.shields.io/badge/Python-3.x-blue?style=flat&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data_Analysis-150458?style=flat&logo=pandas)
![Seaborn](https://img.shields.io/badge/Seaborn-Data_Visualization-3776AB?style=flat)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-11557c?style=flat)

An exploratory data analysis (EDA) and statistical inference project focused on identifying key factors directly influencing gross revenue within the film industry.

---

## 📌 Context & Business Objective

In the entertainment industry, forecasting the financial return of movie productions is critical for strategic decision-making and budget allocation.

The main objective of this project is to transform a historical movie dataset (+6,800 records) into **actionable business insights** by validating hypotheses through:
* Rigorous Data Cleaning & Preprocessing (ETL).
* Exploratory Data Analysis (EDA).
* Statistical correlation modeling (Pearson, Kendall, Spearman) and visual linear regression.

---

## 🛠️ Technologies & Libraries

* **Language:** Python 3.x
* **Data Manipulation & Preprocessing:** `Pandas`, `NumPy`
* **Data Visualization:** `Seaborn`, `Matplotlib`
* **Environment:** Jupyter Notebook / VS Code

---

## 🧹 Data Pipeline & Quality Assurance (ETL)

To ensure **data integrity** and prevent bias in statistical modeling, the following processing steps were implemented:

1. **Missing Data Audit:** Evaluated missing values across all 15 dataset features.
2. **Type Inconsistency Correction:**
   * Converted floating-point variables (`float64`) to integers (`int64`) for key numerical fields such as `budget` and `gross` to optimize storage and align with financial formatting standards.
3. **Date Standardization:**
   * Engineered the `yearcorrect` calculated feature by extracting the release year directly from the `released` date string, resolving discrepancies with the original `year` column.
4. **Categorical Encoding:** Applied numerical encoding (*numerization*) to qualitative variables (company, director, genre, writer) to evaluate their impact within a multivariable correlation matrix.

---

## 📊 Exploratory Data Analysis (EDA) & Key Insights

### 1. Numerical Correlation Evaluation
Calculated Pearson correlation matrices to quantify relationships among quantitative features (`budget`, `gross`, `votes`, `score`, `runtime`).

* **Budget vs. Gross Revenue (`budget` vs. `gross`):**
  * Strong positive correlation (**r ≈ 0.74**).
  * *Insight:* Production budget is the most significant quantitative predictor of gross revenue.
* **Audience Votes vs. Gross Revenue (`votes` vs. `gross`):**
  * Moderate-to-high positive correlation (**r ≈ 0.61**).
  * *Insight:* Audience engagement and popularity (reflected in vote counts) serve as direct catalysts for commercial performance.

### 2. Visual Analytics
* **Linear Regression Scatter Plots:**
  * Implemented `sns.regplot()` scatter plots with regression lines to illustrate clear linear trends between allocated budget and box office performance.
* **Correlation Heatmaps:**
  * Generated multivariable heatmaps using `Seaborn` to translate complex numerical correlations into intuitive visual summaries.

---

## 📁 Repository Structure

```text
├── movies.csv          # Historical movie dataset
├── Movie_Project.ipynb # Interactive Jupyter Notebook with complete analysis
└── README.md           # Technical documentation
