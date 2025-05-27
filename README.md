# DSA210-Term-Project

I am a student at **Sabancı University**, located in **Gebze, Turkey**, and this is my DSA2
10 term project.

Gebze is one of the industrial regions of Turkey and frequently experiences poor air quality. On April 21, 2025, air quality in Gebze was reported as **“Poor”**, with **PM2.5 levels at 27 µg/m³** and **NO₂ levels at 32 µg/m³**, according to AccuWeather. These numbers raise immediate concerns about the long-term effects of such exposure. While we often discuss the physical impacts of air pollution, **what about its impact on mental health?**


<img width="644" alt="Screenshot 2025-04-21 at 7 54 54 PM" src="https://github.com/user-attachments/assets/62bdcf8d-8107-4f33-a4aa-5c7db6fbd04e" />


As a university student living in a region with constant exposure to air pollutants, I wanted to explore a question that directly affects not only me but potentially millions of people around the world:

> **Does air pollution affect mental health on a global scale?**

This project aims to explore the relationship between **air pollution (PM2.5 and NO₂)** and **mental health disorders (depression, anxiety)** using real-world, country-level datasets from Kaggle.

---

## 📚 Contents
- [Motivation](#motivation)
- [Project Goal](#project-goal)
- [Data Sources and Preprocessing](#data-sources-and-preprocessing)
- [Hypotheses](#hypotheses)
- [Analysis Plan](#analysis-plan)
- [Expected Findings](#expected-findings)
- [Limitations and Future Work](#limitations-and-future-work)

---

##  Motivation

Air pollution is a global health concern, well-known for causing respiratory and cardiovascular diseases. However, emerging research suggests it may also play a significant role in **affecting mental health**—such as **depression, anxiety, and cognitive function**. 

Living in Gebze, where the air quality is frequently poor due to heavy industrial activity, I am personally exposed to elevated pollutant levels on a daily basis. This sparked my curiosity about how **chronic exposure to air pollutants** might correlate with **mental health issues** across different regions of the world.

---

## Project Goal

The goal of this project is to:
- Analyze the **correlation between air quality indicators** (PM2.5, NO₂) and **mental health disorder prevalence** (depression, anxiety)
- Test specific hypotheses using statistical analysis
- Build a **predictive model** to estimate mental health outcomes based on pollutant levels

---

##  Data Sources and Preprocessing

This project uses two datasets from **Kaggle**, both smaller than 2 MB and fully public:

### 1. **Air Pollution Dataset**
- **File**: `Air Pollution.csv`
- **Source**: **Kaggle**
- **Size**: **~1 MB**
- **Features**: **Country**, **City**, **Year**, **PM2.5**, **PM10**, **NO₂**, temporal coverage  
- **Processing**:
  - **Filtered out** rows with missing **PM2.5** and **NO₂**
  - **Dropped unnecessary columns** such as *City*, *Latitude*, *Longitude*
  - **Aggregated data** to **country level** by averaging over all cities and years
  - **Created a new variable**: `Pollution Weighted Average = (PM2.5 + NO₂) / 2`
  - This cleaned dataset was merged with the mental health data for final analysis

### 2. **Mental Health Disorders Dataset**
- **File**: `Mental health Depression disorder Data.csv`
- **Source**: **Kaggle**
- **Size**: **~1 MB**
- **Features**: **Country**, **Year**, **Depression (%)**, **Anxiety disorders (%)**, **Bipolar (%)**, **Eating disorders (%)**, **Alcohol use (%)**  
- **Processing**:
  - **Selected only** `Depression (%)` and `Anxiety disorders (%)` columns
  - **Dropped irrelevant columns** (e.g., Bipolar, Alcohol use)
  - **Filtered out missing values**
  - **Standardized country names** to match the air pollution dataset
  - **Averaged by country** to align with the pollution data's aggregation level

### 3. **Merged Clean Dataset**
- **File**: `merged_cleaned_data.csv`
- **Stored in**: `data/` folder
- **Final Features**:
  - `Country`, `PM2.5`, `NO₂`, `Pollution Weighted`, `Depression (%)`, `Anxiety disorders (%)`
- **Purpose**: Used for all hypothesis testing, correlation analysis, and visualizations

---

##  Hypotheses

This project explores whether country-level air pollution indicators (PM2.5 and NO₂) are statistically associated with mental health disorder prevalence, specifically depression and anxiety. The core analysis uses a combined pollution metric (the average of PM2.5 and NO₂) and examines its relationship with two dependent variables: depression (%) and anxiety disorders (%). The hypotheses were tested using Pearson correlation coefficients and evaluated at a 95% confidence level (α = 0.05).

---

### 1. Combined Air Pollution and Depression

**Hypothesis:** Higher air pollution levels are associated with higher depression prevalence across countries.

- **Null Hypothesis (H₀):** There is no significant correlation between the weighted average of PM2.5 and NO₂ and depression rates.
- **Alternative Hypothesis (H₁):** Higher combined air pollution is significantly associated with higher depression rates.

**Test Used:** Pearson correlation  
**Results:**
- Correlation coefficient (r): -0.19
- P-value: 0.1554

**Conclusion:**  
*Fail to reject the null hypothesis.*  
There is no statistically significant relationship between combined air pollution and depression rates (p > 0.05).  
Although a weak negative trend was observed, it is not sufficient to confirm a linear association between pollutant levels and depression prevalence at the global level.

---

### 2. Combined Air Pollution and Anxiety Disorders

**Hypothesis:** Higher air pollution levels are associated with higher anxiety prevalence across countries.

- **Null Hypothesis (H₀):** There is no significant correlation between the weighted average of PM2.5 and NO₂ and anxiety disorder rates.
- **Alternative Hypothesis (H₁):** Higher combined air pollution is significantly associated with higher anxiety disorder rates.

**Test Used:** Pearson correlation  
**Results:**
- Correlation coefficient (r): -0.36
- P-value: 0.00664

**Conclusion:**  
*Reject the null hypothesis.*  
There is a statistically significant moderate negative correlation between combined pollution levels and anxiety rates (p < 0.05).  
Interestingly, the direction of the correlation is negative, which contradicts common expectations. This may be due to confounding regional variables (e.g., economic stress, healthcare systems, or cultural differences in diagnosis/reporting).

---

### Visualization

To better understand the relationships observed during hypothesis testing, the following scatter plots were created. Each plot includes a regression line to show the trend between combined pollution levels and mental health outcomes:

#### 1. Depression (%) vs. Combined Pollution

![depression_vs_pollution](https://github.com/user-attachments/assets/e5b66804-fabc-44ae-a1c8-fced2909e837)

#### 2. Anxiety Disorders (%) vs. Combined Pollution

![anxiety_vs_pollution](https://github.com/user-attachments/assets/4c64162b-f112-4dfe-896e-8fb67b34f8ea)


These plots visually support the hypothesis test results. The anxiety plot shows a clearer downward trend, aligning with the statistically significant moderate negative correlation, while the depression plot reveals a weaker and less consistent pattern.

---

### Interpretation Note

While the second hypothesis shows a statistically significant result, the negative direction warrants deeper exploration. Potential explanations include:

- Unaccounted confounders (e.g., socioeconomic indicators, climate)
- Reverse causality or ecological fallacy in country-level analysis
- Bias in modeled mental health prevalence data

These insights highlight the importance of further analysis using multivariate models and potentially city-level or individual-level datasets for more causal understanding.




Machine Learning Techniques
---------------------------

This section presents the machine learning models used to investigate whether air pollution indicators (PM2.5, NO₂, and their weighted average) can predict the prevalence of depression and anxiety disorders across countries.

* * *

### 1. Linear Regression: Predicting Mental Health from Air Pollution

*   **Objective**: To test if air pollution indicators can linearly explain the prevalence of depression and anxiety disorders.
*   **Why This Model?** A simple, interpretable model that helps identify direct linear relationships.
*   **Features**: PM2.5, NO₂, Pollution Weighted Average
*   **Targets**: Depression (%), Anxiety disorders (%)

#### Results

| Target     | R² Score | RMSE  | MAE  |
|------------|----------|--------|------|
| Depression | 0.05     | 0.71   | 0.60 |
| Anxiety    | -0.10    | 1.25   | 1.05 |

#### Outcome

The linear regression models indicate very weak or no relationship between air pollution and mental health outcomes.

*   Only 5% of the variation in depression can be explained.
*   A negative R² for anxiety suggests the model performs worse than a naive mean prediction.

**Conclusion**: Air pollution alone does not significantly predict mental health rates on a country level.

#### Actual vs Predicted Anxiety (Linear Regression)

![image](https://github.com/user-attachments/assets/53422f68-dd31-48e5-8360-ca1ecbae3358)

* * *

### 2. Random Forest Regressor: Capturing Nonlinear Effects

*   **Objective**: To model complex, nonlinear relationships between pollutants and mental health disorders.
*   **Why This Model?** Non-parametric, robust, and provides variable importance.
*   **Features**: PM2.5, NO₂, Pollution Weighted Average
*   **Targets**: Depression (%), Anxiety disorders (%)

#### Results

| Target     | R² Score | RMSE  | MAE  |
|------------|----------|--------|------|
| Depression | 0.54     | 0.49   | 0.39 |
| Anxiety    | 0.35     | 0.97   | 0.73 |

#### Outcome

Random Forest shows moderate predictive ability, especially for depression.

*   Explains 54% of variance in depression rates.
*   Explains 35% of variance in anxiety rates.

**Conclusion**: Air pollution may influence mental health, particularly depression, but it's likely not the sole driver.

* * *

### 3. Ridge Regression: A Regularized Linear Baseline

*   **Objective**: To improve upon basic linear regression by mitigating multicollinearity.
*   **Why This Model?** Regularizes coefficients of correlated features (e.g., PM2.5 and NO₂).
*   **Target**: Depression (%)

#### Results

| Target     | R² Score | RMSE  | MAE  |
|------------|----------|--------|------|
| Depression | 0.05     | 0.71   | 0.60 |

#### Outcome

Ridge regression yields no performance improvement over standard linear regression.

**Conclusion**: Regularization alone is not enough — the lack of linear relationship remains the limiting factor.

* * *

### Summary

*   Linear models (Linear/Ridge) are insufficient for capturing the complexity of the relationship between air pollution and mental health.
*   Random Forest outperforms, especially for depression, suggesting a moderate nonlinear link.
*   Anxiety appears to be less influenced by pollution, possibly due to other social, cultural, or economic factors not included in this dataset.


## Analysis Plan

The project will follow a structured pipeline:

### 1. **Exploratory Data Analysis (EDA)**
- Visualize pollutant distributions across countries
- Plot mental health disorder prevalence over time
- Create heatmaps of variable correlations

### 2. **Hypothesis Testing**
- Conduct **Pearson correlation** tests for each hypothesis
- Evaluate significance using **p-values** at α = 0.05

### 3. **Modeling**
- Build a **Multiple Linear Regression model** to predict depression and anxiety rates from PM2.5 and NO₂
- Evaluate model using **R²**, **MAE**, and **RMSE**

---

## 🔍 Expected Findings

Based on existing literature and preliminary trends:
- PM2.5 is expected to have a **positive correlation** with both depression and anxiety
- NO₂ exposure is also anticipated to affect **anxiety prevalence** more strongly
- Bipolar and eating disorders may show **weaker or no correlation**

These findings could indicate that **chronic air pollution exposure** is not only a physical health risk but also a **major psychological stressor**.

---

###  Interpretation Note:
While multiple statistically significant relationships were identified, most showed a **negative correlation**, which contrasts with common assumptions. This could suggest:
- **Confounding factors** not included in this analysis (e.g., GDP, urban stress, healthcare access)
- Possible **data estimation artifacts** from model-based mental health prevalence
- The need for **regional or individual-level data** for causal clarity

---

## **Limitations and Future Work**

### **Limitations**
- **Country-level data** may mask within-country differences and individual-level patterns. Mental health outcomes can vary significantly between regions, especially in large or diverse countries.
- The **mental health data** used is primarily **modeled or estimated** by global institutions, not derived from standardized clinical surveys. This could introduce bias or smoothing.
- Key **confounding variables** such as GDP per capita, education, healthcare access, urbanization, and climate factors are not included in the current model.
- Temporal alignment between pollution and mental health data is approximate — they may not always correspond to the exact same year.
- PM2.5 and NO₂ are important, but not exhaustive — other pollutants (e.g., ozone, sulfur dioxide) were not considered.

---

### **Future Work**
- **Integrate additional socioeconomic features**, including:
  - **GDP per capita**, **education levels**, **unemployment rates**, and **stress indices**
  - This would help isolate the effect of pollution from other structural factors.
- Transition to **regional or city-level data**, where possible, to improve granularity and identify local health risks more precisely.
- Leverage **panel datasets** (over multiple years) to analyze trends and strengthen **causal inference** through longitudinal methods.
- Apply **machine learning** models for multivariate analysis and predictive modeling.
- Consider interactive dashboards (e.g., Streamlit, Dash) to allow users to explore pollution–mental health relationships by country or year.


---
## 🧠 Final Note

This project stems from a personal and academic interest in understanding the **invisible connections between our environment and our minds**. Living in an area like Gebze, where air pollution is a daily reality, raises the question:

> *Can the air we breathe affect our mood, our focus, our mental state?*

Using global datasets and analytical tools, this project takes a step toward answering that question.

