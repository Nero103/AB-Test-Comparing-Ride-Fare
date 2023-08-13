# AB-Test-Comparing-Ride-Fare
This is an A/B test to compare the ride service fare payments to find which one generates the most revenue.

# Overview
This is a project on the New York City Taxi and Limousine Commission data. The goal was to determine which payment type (credit card and cash) generates the most revenue using existing data that was collected over the course of a year. An A/B two-sample t-test was used to find a statistically significant difference between the means of the payment types based on total fare amounts per ride, which showed a **mean of 17.66 for credit card** payments and **mean of 13.54 for cash payments**. The test achieved a t-score of **20.34** and a **p-value of 4.53e-91** (or 0.00000000453). These findings suggest, with a significance level set to 5%, that there is a statistically significant difference in the revenue gained between credit card and cash payments.

# Business Understanding
The company wants to optimize revenue. By determining, through statistical analysis, the payment type that generates the most revenue, the company can focus on encouraging one payment type over the other.

# Conclusion
With credit card payment being found to be the statistically significant payment type, the company can encourage customers to pay by credit card. This strategy would generate more revenue from ride services. However, this project assumes that passengers were forced to pay by credit card or cash, and once informed of this requirement, they always complied with it.
