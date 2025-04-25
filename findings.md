## Findings
All analyses below are based on a 0.05 significance level. If the p-value < 0.05, the null hypothesis is rejected. Otherwise, we fail to reject the null hypothesis. Additionally, the strength and direction of the correlation are interpreted using the Pearson correlation coefficient (r).

## Top 20 Bar Charts

## Top 20 Countries by Anxiety Disorder Rates
![image](https://github.com/user-attachments/assets/9f02a972-08ed-4664-aefe-bef8eb0e3f61)

Dataset Used: Contains country-level percentages of people experiencing anxiety disorders.

Chart Description:

The x-axis represents the percentage of people suffering from anxiety disorders in each country.

The y-axis lists the Top 20 countries with the highest anxiety rates.

The chart is sorted in descending order, with New Zealand having the highest anxiety disorder rate, followed by Norway and France.

## Top 20 Countries by Depression Rates
 ![image](https://github.com/user-attachments/assets/d55a3033-2100-4ac1-b1be-391bb26dbd60)
 
Dataset Used: Contains country-level data on the prevalence of depression.

Chart Description:

The x-axis represents the percentage of people affected by depression in each country.

The y-axis lists the Top 20 countries with the highest reported depression rates.

The chart is sorted from highest to lowest, with Finland, Australia, and Portugal leading the list.

## Top 20 Countries by Pollution Average (PM2.5 + NO₂)

![image](https://github.com/user-attachments/assets/4224807d-736d-4742-82c9-c9f3a4adbd35)

Dataset Description:
The dataset includes country-level measurements of PM2.5 (fine particulate matter) and NO₂ (nitrogen dioxide) pollution levels.

Data Processing:
A weighted average of PM2.5 and NO₂ values is computed for each country to produce a single representative pollution score. This combined metric is used to reflect the overall pollution burden by integrating the impact of both pollutants.

Chart Description:

The x-axis represents the computed pollution average for each country.

The y-axis displays the Top 20 countries ranked by this pollution average.

The countries are sorted in descending order, with Mongolia, Kuwait, and Bangladesh appearing at the top, indicating the highest pollution levels according to the combined metric.

## PM2.5 vs Depression (%)
![image](https://github.com/user-attachments/assets/ff1b6e68-1974-42f3-8543-a1c8e53e42bf)
Pearson r: -0.22

p-value: 0.09918

Interpretation: There is a weak negative correlation between PM2.5 and depression rates.

Statistical Decision: Fail to reject the null hypothesis.

Comment: The relationship is not statistically significant. While there appears to be a slight trend showing that higher PM2.5 levels may correlate with lower depression percentages, the evidence is not strong enough to confirm a significant association.



## PM2.5 vs Anxiety Disorders (%)
![image](https://github.com/user-attachments/assets/edace363-2b80-46a9-8104-7e598fb39b6c)
Pearson r: -0.42

p-value: 0.0011

Interpretation: A moderate negative correlation is observed.

Statistical Decision: Reject the null hypothesis.

Comment: This result is statistically significant and suggests that higher PM2.5 levels are associated with lower anxiety disorder prevalence, which contradicts initial expectations. This could be due to other confounding societal or environmental factors.

## NO2 vs Depression (%)
![image](https://github.com/user-attachments/assets/c43dfa0c-2a75-4466-ae67-8d122f66f239)
Pearson r: -0.10

p-value: 0.45469

Interpretation: Very weak negative correlation.

Statistical Decision: Fail to reject the null hypothesis.

Comment: There is no statistically significant relationship between NO2 levels and depression rates. The data does not provide evidence for any association.

## NO2 vs Anxiety Disorders (%)
![image](https://github.com/user-attachments/assets/46e19453-ce2b-4b6a-9ff9-c8c45ae9bea0)
Pearson r: -0.17

p-value: 0.20127

Interpretation: Weak negative correlation.

Statistical Decision: Fail to reject the null hypothesis.

Comment: NO2 levels do not show a significant impact on anxiety disorders. Although the slope is negative, this might be due to randomness.


## Pollution Average (PM2.5 + NO2) vs Depression (%)
![image](https://github.com/user-attachments/assets/11082e24-b749-48ac-be95-7194493ae9b9)
Pearson r: -0.19

p-value: 0.1554

Interpretation: Weak negative correlation.

Statistical Decision: Fail to reject the null hypothesis.

Comment: Averaged pollution level does not significantly explain depression percentages. The relationship is weak and not statistically meaningful.


## Pollution Average (PM2.5 + NO2) vs Anxiety Disorders (%)
![image](https://github.com/user-attachments/assets/15523eff-59b4-4057-92d9-096170c33a1f)
Pearson r: -0.36

p-value: 0.00664

Interpretation: Moderate negative correlation.

Statistical Decision: Reject the null hypothesis.

Comment: This indicates a statistically significant negative relationship. Countries with higher overall pollution levels tend to have lower anxiety disorder prevalence, suggesting potentially reversed causation or missing confounding variables.


![image](https://github.com/user-attachments/assets/2246516a-8fea-4ac7-b3e1-87ffea9fe452)
- *Intersection Analysis**: Only Lebanon appears in the top 20 for all three categories (pollution, anxiety, depression).

- *Comment**: Most countries are only top-ranked in one or two categories, showing limited overlap between mental health burden and pollution exposure. This again highlights the complexity and multi-factorial nature of mental health disorders.

## Scatter Plots – Pollution Avg vs Depression/Anxiety
![image](https://github.com/user-attachments/assets/84f83d4b-6c5a-48c3-948e-88c9996a0bbc)

![image](https://github.com/user-attachments/assets/5bc0d86c-e74f-4009-83be-eabc884d52ef)
These reinforce previously observed trends. Depression shows a slight negative trend with pollution average, but anxiety demonstrates a clearer downward slope, aligning with the significant Pearson correlation found earlier.


## Boxplot – Pollution and Mental Health Indicators
![image](https://github.com/user-attachments/assets/5a54590f-9fb9-48ee-be3e-2b9c83740237)
Interpretation: PM2.5 and NO2 have wide spreads and clear outliers. Depression and anxiety distributions are tightly packed between 2–5% and 3–6% respectively.

Comment: The narrow range of mental health values may be a limiting factor in detecting stronger correlations with air pollution.


## Histograms
![image](https://github.com/user-attachments/assets/5d01f78c-3ccc-4ceb-a93f-9889cea3b3ae)
![image](https://github.com/user-attachments/assets/f124e9bd-3cfd-4cd9-a33b-bff55491bc42)
Anxiety: Right-skewed distribution with a peak around 5%.

Depression: Also slightly skewed with a peak around 3.5%.

Comment: These distributions confirm that most countries have moderate anxiety and depression rates, making outliers (e.g., Lebanon or Finland) stand out in visualizations.

## Heatmap of Correlations
![image](https://github.com/user-attachments/assets/412f764b-b55b-4ceb-a37d-1dc915544bef)
Key Values:

PM2.5–Anxiety: -0.42 ✅ significant

Pollution Avg–Anxiety: -0.36 ✅ significant

PM2.5–Depression: -0.22 ❌ not significant

NO2–Mental Health: very weak

Comment: The heatmap provides a useful visual summary. While PM2.5 and Pollution Average show moderate negative relationships with anxiety, other associations remain weak or statistically inconclusive.

## Statistically Significant Findings:

PM2.5 and Anxiety

Pollution Average and Anxiety

Null Hypothesis Rejected: For only 2 out of 6 hypotheses.

Interpretation: Air pollution may have some inverse association with anxiety rates globally, but depression shows no meaningful correlation.

Caution: Unexpected trends and weak correlations suggest more granular (e.g., individual-level) or longitudinal data are needed to draw definitive conclusions.












