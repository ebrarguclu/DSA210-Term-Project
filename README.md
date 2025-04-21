# DSA210-Term-Project

I am a student at **Sabancı University**, located in **Gebze, Turkey**, and this is my DSA210 term project.

Gebze is one of the industrial regions of Turkey and frequently experiences poor air quality. On April 21, 2025, air quality in Gebze was reported as **“Poor”**, with **PM2.5 levels at 27 µg/m³** and **NO₂ levels at 32 µg/m³**, according to AccuWeather. These numbers raise immediate concerns about the long-term effects of such exposure. While we often discuss the physical impacts of air pollution, **what about its impact on mental health?**

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
- **Source**: Kaggle
- **Size**: ~1 MB
- **Features**: `Country`, `City`, `Year`, `PM2.5`, `PM10`, `NO₂`, temporal coverage
- **Processing**:
  - Filtered out rows with missing `PM2.5` and `NO₂`
  - Aggregated data to country level to align with mental health data

### 2. **Mental Health Disorders Dataset**
- **File**: `Mental health Depression disorder Data.csv`
- **Source**: Kaggle
- **Size**: ~1 MB
- **Features**: `Country`, `Year`, `Depression %`, `Anxiety %`, `Bipolar %`, `Eating disorders %`, `Alcohol use %`
- **Processing**:
  - Selected `Depression` and `Anxiety` columns for analysis
  - Matched by `Country` and `Year` with air quality dataset

---

## 🧪 Hypotheses

This project will examine the following **four statistical hypotheses**:

### H1: PM2.5 Levels and Depression
> **H₀:** PM2.5 concentration does not significantly correlate with depression rates.  
> **H₁:** Higher PM2.5 levels are associated with higher depression rates.

---

### H2: NO₂ Levels and Anxiety Disorders
> **H₀:** NO₂ concentration does not significantly correlate with anxiety disorder rates.  
> **H₁:** Higher NO₂ levels are associated with higher anxiety disorder rates.

---

### H3: PM2.5 Levels and Anxiety Disorders
> **H₀:** PM2.5 levels do not correlate with anxiety disorder prevalence.  
> **H₁:** Higher PM2.5 exposure is associated with increased anxiety disorder prevalence.

---

### H4: NO₂ Levels and Depression
> **H₀:** NO₂ concentration does not significantly correlate with depression rates.  
> **H₁:** Higher NO₂ exposure is associated with higher depression rates.

---

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

##  Limitations and Future Work

###  Limitations
- **Country-level data** may mask individual-level effects
- Mental health data is **modeled** or **estimated**, not survey-based
- Confounding variables (e.g., income level, healthcare access) are not included

###  Future Work
- Integrate additional features: GDP, education levels, stress indices
- Use regional (city-level) data for more granular insight
- Explore long-term panel datasets for **causal inference**

---
## 🧠 Final Note

This project stems from a personal and academic interest in understanding the **invisible connections between our environment and our minds**. Living in an area like Gebze, where air pollution is a daily reality, raises the question:

> *Can the air we breathe affect our mood, our focus, our mental state?*

Using global datasets and analytical tools, this project takes a step toward answering that question.

