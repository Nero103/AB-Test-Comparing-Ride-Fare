# AB-Test-Comparing-Ride-Fare

Statistical A/B testing project analyzing New York City TLC ride payment data to determine whether credit card or cash payments generate higher ride revenue.-

# Overview

This project analyzes New York City Taxi and Limousine Commission (TLC) ride data to evaluate the relationship between payment type and total ride revenue. The goal was to determine whether customers paying by credit card or cash generated significantly different average fare amounts.

Using Python, exploratory data analysis (EDA), and a two-sample t-test, the project compared the average total ride amounts between credit card and cash transactions.

The analysis found that:

* Credit card payments averaged approximately **$17.66** per ride
* Cash payments averaged approximately **$13.55** per ride
* The test produced a **t-statistic of 20.35**
* The resulting **p-value was 4.53e-91**

With a significance level of 5%, the findings indicate a statistically significant difference between the two payment methods.


# Business Understanding

The New York City TLC wanted to better understand which payment type generated more revenue in order to support future operational or payment-related business strategies.

The project focused on answering the question: Is there a statistically significant difference in total fare amount between customers paying by credit card and customers paying by cash?


# Tools & Libraries Used

* Python
* Jupyter Notebook
* Pandas
* NumPy
* SciPy
* Matplotlib


# Project Workflow

## 1. Data Loading & Preparation

The dataset was imported into Python using Pandas for analysis.

```python
import pandas as pd
taxi_data = pd.read_csv("2017_Yellow_Taxi_Trip_Data.csv", index_col=0)
```

## 2. Exploratory Data Analysis (EDA)

Descriptive statistics were used to better understand the distribution of ride and payment data.

```python
taxi_data.describe(include='all')
```

### The analysis showed:

Credit card transactions were the most common payment type
The average total ride amount across all rides was approximately $16.31
Several outliers existed in fare-related fields

Payment type counts:

|Payment Type |	Count|
|------------|--------|
|Credit Card	| 15,265|
|Cash | 7,267|
|No Charge |	121|
|Dispute	| 46|

## 3. Hypothesis Testing

A two-sample t-test was conducted to compare average total ride amounts between:

* credit card payments
* cash payments

### Null Hypothesis (H0)

There is no statistically significant difference in average total ride amount between credit card and cash payments.

### Alternative Hypothesis (H1)

There is a statistically significant difference in average total ride amount between credit card and cash payments.

The significance level was set to:

```python
significance_level = 0.05
```

# Statistical Test

```python
from scipy import stats

t_stats, p_value = stats.ttest_ind(
    a=credit_card['total_amount'],
    b=cash['total_amount'],
    equal_var=False
)
```

## Results

| Metric |	Value|
|--------|-------|
|Credit Card Mean |	$17.66|
|Cash Mean |	$13.55|
|t-statistic|	20.35|
|p-value|	4.53e-91|

Since the p-value (4.53 x 10^-91) was significantly lower than the 5% significance threshold, the null hypothesis was rejected.

# Key Findings

* Customers paying by credit card generated higher average total ride amounts than customers paying by cash.
* The difference between payment methods was statistically significant.
* Credit card payments were associated with higher total revenue overall.

# Important Analytical Considerations

This analysis was conducted using historical observational data rather than a true randomized experiment.

Several important limitations were identified:

* Riders were not randomly assigned a payment method
* Longer trips may naturally favor credit card usage
* Cash tips may not have been fully captured in the dataset
* Total amount includes tips, which may inflate differences between payment types

Because of these factors, the analysis demonstrates correlation rather than direct causation.

Future analysis could compare:

* base fare amount instead of total amount
* trip distance by payment type
* tip behavior separately from fare revenue

# Conclusion

The analysis found a statistically significant difference between credit card and cash ride payments, with credit card transactions generating higher average total ride amounts.

While the findings suggest that encouraging credit card payments could increase ride revenue, the project also highlights the importance of understanding observational data limitations and potential confounding variables when interpreting statistical results.
