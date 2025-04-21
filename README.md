DSA210 Term Project – Fethiye Ebrar Güçlü
Project Title: Air You Breathe, Mood You Feel 
Overview
This term project investigates the connection between environmental pollution, socioeconomic disparities, and mental health outcomes in the United States. The project leverages real-world datasets to analyze how environmental stressors such as air quality interact with income level, poverty rates, and educational attainment to influence the mental well-being of individuals across U.S. states. Through rigorous data preprocessing, hypothesis testing, and machine learning techniques, this study aims to contribute data-driven insights to the growing body of research on public mental health.
 
Motivation
Mental health issues are on the rise globally, and many external factors—particularly environmental pollution and social inequality—have been implicated in worsening conditions such as depression, anxiety, and chronic stress. However, these factors are rarely studied together using large-scale data. By combining environmental and socioeconomic datasets, this project aims to uncover patterns that would otherwise remain hidden, encouraging more nuanced and localized public health interventions.
 
Project Goal
•	To explore how varying levels of air pollution (e.g., PM2.5, NO2) relate to mental health conditions like depression and frequent distress.
•	To evaluate the moderating role of socioeconomic indicators (e.g., income, education, poverty rate) in this relationship.
•	To apply statistical and machine learning techniques to build predictive models of mental health outcomes.
 
Data Sources and Preprocessing
The datasets used in this project were gathered from public platforms such as Kaggle and cleaned for analysis using Python.
1. Air Quality
•	Dataset Source: Kaggle – US Pollution Data (2014–2017)
•	Dataset Name: Air Quality Dataset
•	Columns Used: PM2.5, O3, NO2, SO2, CO
•	Explanation: These columns represent daily pollutant concentrations in U.S. cities. PM2.5 and NO2 are of particular interest due to their documented correlation with mental and respiratory health risks. Data was averaged by state to align with mental health statistics.
2. Mental Health Outcomes
•	Dataset Source: Kaggle – Mental Health in the US by State
•	Dataset Name: Mental Health Dataset
•	Columns Used: depression_percentage, frequent_mental_distress, access_to_care
•	Explanation: This dataset includes the percentage of adults in each state experiencing depression and frequent mental distress. It also includes data on access to mental health care.
3. Socioeconomic Demographics
•	Dataset Source: Kaggle – US Census Demographic Data
•	Dataset Name: Demographics Dataset
•	Columns Used: median_income, poverty_rate, education_level, population_density
•	Explanation: Socioeconomic indicators were used to explore disparities across states. This allowed for assessing whether social conditions amplify or buffer the impact of environmental stressors.
All datasets were merged by state and year (where available) to create a unified data table. Null values were either imputed with group averages or excluded depending on the column's criticality.
 
Data Analysis
1. Exploratory Data Analysis (EDA)
•	Heatmaps were used to explore correlations between variables such as PM2.5 and depression rates.
•	Boxplots compared air quality distributions across states with high vs. low mental distress.
•	Scatterplots and regression lines were used to visualize trends.
2. Hypothesis Testing
•	Hypothesis 1: Higher PM2.5 levels are significantly associated with increased depression percentage.
•	Hypothesis 2: The strength of this association is greater in states with lower median income and higher poverty rates.
•	Methods used: Pearson correlation, linear regression, interaction term analysis
3. Machine Learning Models
•	Objective: Predict depression percentage using pollution and demographic indicators.
•	Models: Linear Regression, Random Forest Regressor
•	Metrics: R², RMSE, MAE
•	Insights: Feature importance analysis highlighted PM2.5 and poverty rate as top predictors.
 
Findings
•	It may be expected that higher PM2.5 levels are positively correlated with increased depression rates across states.
•	States with lower income and higher poverty may experience a stronger association between air pollution and mental distress.
•	Predictive models such as Random Forest and Linear Regression might help uncover important features, where pollutants and poverty could emerge as dominant predictors.
•	Socioeconomic variables such as education level may have a buffering effect on the negative impacts of pollution on mental health.
 
Limitations and Future Work
Limitations
•	Aggregated state-level data may obscure local disparities.
•	Mental health data is annual, whereas pollution data is daily, requiring time-averaging.
•	Mental health diagnosis is self-reported and may contain underreporting bias.
Future Work
•	Integrate more granular (county-level) data for precision analysis.
•	Include other environmental factors such as noise, green space, or extreme temperature.
•	Apply time-series analysis or causal inference methods.
 
Repository Structure
/data               # Raw and cleaned datasets
/notebooks          # Jupyter notebooks for EDA and modeling
/scripts            # Python scripts for data merging and visualization
/visualizations     # Figures, graphs, and exported visual summaries
README.md           # Project documentation
requirements.txt    # Python dependency list

