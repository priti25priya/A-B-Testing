# A-B-Testing
A/B Testing (Marketing Campaign)
# A/B Testing: Facebook vs. AdWords Campaign Optimization
> **Objective:** Evaluating the effectiveness of Facebook and AdWords platforms to optimize marketing spend and maximize ROI.

## 📌 Project Overview (STAR Method)

### Situation
The project addressed a challenge faced by a marketing agency managing two parallel advertising campaigns (Facebook and AdWords) in 2019. The primary requirement was to identify which platform provided superior results to guide budget allocation for the subsequent fiscal year.

### Task
The objective was to perform a statistically rigorous A/B test comparing performance metrics—specifically clicks and conversions—between the two platforms. The analysis aimed to identify performance patterns and establish whether observed differences were statistically significant.

### Action
* **Data Engineering:** Processed a 365-day dataset of performance metrics, including data cleaning and time-series formatting for consistency.
* **Exploratory Data Analysis (EDA):** Leveraged `Seaborn` and `Matplotlib` to identify distribution patterns. A custom categorization function was implemented to segment daily performance, revealing that Facebook achieved a higher frequency of "High-Conversion" days (10+ sales).
* **Statistical Hypothesis Testing:** * Conducted a **Shapiro-Wilk test** to assess normality; the data was found to be non-normally distributed ($p < 0.05$).
    * Employed the **Mann-Whitney U test** (a non-parametric alternative) to compare the means of the two campaigns, ensuring that findings were not the result of random variance.
* **Predictive Modeling:** Developed **Linear Regression** models to quantify the relationship between ad clicks and conversions, yielding an R-squared of 0.77 for the Facebook campaign.
* **Cointegration Analysis:** Performed the **Engle-Granger test** to determine the long-term equilibrium relationship between advertising spend and conversions.

### Result
* **Performance Leadership:** Facebook emerged as the more effective platform for scaling, showing a significantly higher volume of conversions.
* **Statistical Significance:** The null hypothesis was rejected ($p < 0.05$), confirming a statistically significant difference in platform performance.
* **Strategic Insight:** Established a long-term stable relationship between cost and conversions, providing a data-driven framework for optimizing daily bidding strategies and budget reallocation.

---

## 🛠 Tech Stack & Libraries
* **Python:** Core analytical language.
* **Pandas:** Data manipulation and feature engineering.
* **Scipy.stats:** Statistical hypothesis testing (Shapiro, Mann-Whitney U).
* **Scikit-Learn:** Predictive linear modeling.
* **Statsmodels:** Cointegration and advanced statistical modeling.
* **Matplotlib/Seaborn:** Data visualization.

---

## 📊 Key Analytical Findings

### 1. Conversion Distribution Comparison
The analysis categorized daily performance to highlight the density of sales across both platforms. Facebook consistently occupied higher tiers of conversion volume compared to AdWords.

| Conversion Category | Facebook (Days) | AdWords (Days) |
| :--- | :--- | :--- |
| Less than 6 | 60 | 148 |
| 6 - 10 | 163 | 217 |
| 10 - 15 | 100 | 0 |
| More than 15 | 42 | 0 |

### 2. Hypothesis Testing Summary
| Test | Metric | Result | Decision |
| :--- | :--- | :--- | :--- |
| Shapiro-Wilk | Normality | $p < 0.05$ | Use Non-Parametric Test |
| Mann-Whitney U| Clicks/Conversions | $p < 0.05$ | Reject Null Hypothesis |
| Engle-Granger | Cointegration | $p < 0.05$ | Long-term Equilibrium Exists |

---

## 🚀 Usage
1. Clone the repository.
2. Install dependencies: `pip install pandas matplotlib seaborn scipy scikit-learn statsmodels`.
3. Execute the analysis: `jupyter notebook "AB Testing (Marketing Campaigns).ipynb"`.
