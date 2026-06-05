# Python Coding Questions (Product DS)

Not LeetCode-style algorithms. Product DS coding tests data manipulation, analysis, and statistical implementation.

---

## Data Manipulation (pandas)

1. Given a DataFrame of user events (user_id, event_type, timestamp), calculate 7-day retention rate.
2. Compute rolling 7-day average revenue per user from a transactions table.
3. Given user sessions data, identify users whose session frequency decreased >50% month-over-month.
4. Pivot a long-format event log into a user-feature matrix for analysis.
5. Merge two DataFrames (users and orders) and compute lifetime value per user cohort.
6. Handle missing data: given a DataFrame with NaN values, implement 3 different imputation strategies and explain trade-offs.

## Statistical Analysis

7. Implement a two-sample t-test from scratch. Compare results with scipy.stats.
8. Write a function to calculate sample size needed for an A/B test given: baseline rate, MDE, alpha, power.
9. Implement bootstrap confidence intervals for median revenue per user.
10. Given experiment data (control/treatment groups), compute p-value, confidence interval, and effect size.
11. Implement a chi-squared test for independence on categorical data.
12. Write a permutation test to compare two groups when normality assumption is violated.

## Experiment Analysis

13. Given raw A/B test data, perform full analysis: check balance, compute metrics, test significance, report results.
14. Detect and handle outliers in experiment data. Show impact on results with/without outlier treatment.
15. Implement a sequential testing procedure (show how to check results before full sample is collected).
16. Given multi-variant test data (A/B/C/D), apply multiple testing correction and report results.
17. Analyze an experiment with ratio metrics (e.g., revenue per session). Handle the delta method.
18. Implement CUPED (Controlled-experiment Using Pre-Experiment Data) variance reduction.

## Modeling & Analysis

19. Build a simple logistic regression to predict user churn. Interpret coefficients.
20. Implement cohort analysis: compute retention curves for monthly cohorts.
21. Segment users using k-means clustering on behavioral features. Interpret clusters.
22. Build a metric decomposition: break down revenue change into volume, mix, and rate effects.
23. Implement anomaly detection on a time series of daily active users.
24. Given funnel data, identify the biggest drop-off point and quantify the opportunity.

---

## Libraries to Know
- **pandas** — data manipulation (80% of coding rounds)
- **numpy** — numerical operations
- **scipy.stats** — statistical tests
- **statsmodels** — regression, time series
- **matplotlib/seaborn** — visualization (sometimes asked to sketch)
- **sklearn** — basic modeling (logistic regression, clustering)

## Tips
- Write clean, readable code — use meaningful variable names
- Explain your approach BEFORE coding
- Handle edge cases: empty DataFrames, NaN values, division by zero
- Show you can go from raw data → insight → recommendation
- Practice in Jupyter notebooks to simulate interview environment
