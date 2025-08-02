# Medical Charges Cost Analysis — EDA, Statistical Testing & Risk Segmentation

This project explores the drivers of individual medical insurance charges through **exploratory data analysis**, **statistical testing**, and **risk-based clustering**—both manual and unsupervised.

---

## Overview

* Extensive EDA of demographics, lifestyle, and cost data
* Statistical hypothesis testing (ANOVA, Chi-square) to validate observed trends
* **Risk group segmentation** using:

  * **Manual clustering** based on domain insights (smoker, BMI, charges)
  * **K-Means (unsupervised learning)** with Elbow Method
* Feature importance analysis using Random Forest

---

## Dataset

* **Source**: [Kaggle - Medical Cost Personal Dataset](https://www.kaggle.com/datasets/mirichoi0218/insurance)
* **Rows**: 1,338 individuals
* **Features**: age, sex, bmi, children, smoker, region, charges

---

## Key Insights

* **Smoker status** is the most influential factor (r ≈ 0.76)
* **Obesity** (BMI ≥ 30) is strongly associated with higher charges
* **Age** contributes moderately to cost variation
* No strong evidence that region or age group predicts smoking behavior

---

## Statistical Tests Summary

| Test Type  | Comparison                    | Result        |
| ---------- | ----------------------------- | ------------- |
| ANOVA      | Charges by BMI, sex, age      | Significant   |
| ANOVA      | BMI by smoker, sex, age group | Significant   |
| Chi-square | Smoker \~ sex                 | Dependent     |
| Chi-square | Smoker \~ region, age group   | Not dependent |

---

## Risk Segmentation Approaches

### Manual Clustering (Rule-Based)

Manually defined 3 risk groups based on domain logic:

* **Low Risk**: Non-smokers, BMI < 35, low charges
* **Medium Risk**: Smokers with BMI < 30, moderate charges
* **High Risk**: Smokers with BMI ≥ 30, high charges

Each group was analyzed by age and sex distributions for interpretation.

---

### K-Means Clustering (Unsupervised)

* Selected features: BMI, smoker (encoded), charges
* Used **Elbow Method** to select **k = 3**
* Clusters closely matched manual risk tiers:

  * Cluster 0: Low Risk
  * Cluster 1: Medium Risk
  * Cluster 2: High Risk

---

## Tools Used

* **Visualization & EDA**: pandas, seaborn, matplotlib
* **Statistical Analysis**: scipy.stats
* **Clustering**: KMeans (`scikit-learn`), Elbow Method
* **Modeling**: Random Forest for feature importance

---

## Takeaways

* Lifestyle factors like **smoking** and **BMI** are dominant cost drivers
* **Clustering effectively stratifies individuals into actionable risk profiles**
* Findings support preventive health strategies, insurance modeling, and cost forecasting
