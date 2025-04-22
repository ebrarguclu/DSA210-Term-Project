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

## 🧪 Hypotheses

## ***This project will examine the following six statistical hypotheses:***

### **H1: PM2.5 Levels and Depression**
> **H₀:** PM2.5 concentration does not significantly correlate with depression rates.  
> **H₁:** Higher PM2.5 levels are associated with higher depression rates.

---

### **H2: NO₂ Levels and Anxiety Disorders**
> **H₀:** NO₂ concentration does not significantly correlate with anxiety disorder rates.  
> **H₁:** Higher NO₂ levels are associated with higher anxiety disorder rates.

---

### **H3: PM2.5 Levels and Anxiety Disorders**
> **H₀:** PM2.5 levels do not correlate with anxiety disorder prevalence.  
> **H₁:** Higher PM2.5 exposure is associated with increased anxiety disorder prevalence.

---

### **H4: NO₂ Levels and Depression**
> **H₀:** NO₂ concentration does not significantly correlate with depression rates.  
> **H₁:** Higher NO₂ exposure is associated with higher depression rates.

---

### **H5: Combined Air Pollution and Depression**
> **H₀:** The weighted average of PM2.5 and NO₂ is not significantly correlated with depression rates.  
> **H₁:** Higher combined air pollution levels are associated with higher depression rates.

---

### **H6: Combined Air Pollution and Anxiety Disorders**
> **H₀:** The weighted average of PM2.5 and NO₂ is not significantly correlated with anxiety disorder rates.  
> **H₁:** Higher combined air pollution levels are associated with higher anxiety disorder rates.

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

##  Summary of Findings

All six hypotheses were tested using **Pearson correlation** at a **95% confidence level (α = 0.05)**. Below is a summary of the correlation strength (r), p-values, and statistical interpretations:

---

### **H1: PM2.5 Levels and Depression**
- **r = -0.22**
- **p = 0.09918**
- **Conclusion**: *Fail to reject H₀*. No significant correlation between PM2.5 and depression.  
  Although a weak negative trend exists, the result is **not statistically significant** at the 0.05 level.

---

### **H2: PM2.5 Levels and Anxiety Disorders**
- **r = -0.42**
- **p = 0.0011**
- **Conclusion**: *Reject H₀*. There is a **moderate negative correlation** between PM2.5 levels and anxiety disorder prevalence.  
  This result is **statistically significant**, though the inverse direction is unexpected and worth further exploration.

---

### **H3: NO₂ Levels and Depression**
- **r = -0.10**
- **p = 0.45469**
- **Conclusion**: *Fail to reject H₀*. No significant correlation between NO₂ and depression.  
  The correlation is negligible and **not statistically significant**.

---

### **H4: NO₂ Levels and Anxiety Disorders**
- **r = -0.17**
- **p = 0.20127**
- **Conclusion**: *Fail to reject H₀*. Weak negative correlation, but **not statistically significant**.

---

### **H5: Combined Pollution and Depression**
- **r = -0.19**
- **p = 0.1554**
- **Conclusion**: *Fail to reject H₀*. The combined pollution score does **not significantly predict** depression rates.

---

### **H6: Combined Pollution and Anxiety Disorders**
- **r = -0.36**
- **p = 0.00664**
- **Conclusion**: *Reject H₀*. There is a **statistically significant moderate negative correlation** between combined pollution (PM2.5 + NO₂) and anxiety.  
  The direction again appears **negative**, which may indicate confounding influences or reverse effects in different regions.

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

