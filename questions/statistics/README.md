# Statistics & Probability Questions

Core category for Product DS interviews. Interviewers want you to connect abstract concepts to real product scenarios.

---

## Probability

1. You flip a fair coin 10 times. What's the probability of getting exactly 7 heads?
2. A user visits your site 5 times a day on average (Poisson). What's the probability they visit 0 times tomorrow?
3. 1% of users have a rare bug. Your detector has 95% sensitivity and 90% specificity. A user is flagged — what's the probability they actually have the bug? (Bayes)
4. You draw 2 cards from a deck without replacement. What's P(both are aces)?
5. Three friends independently have a 40% chance of attending an event. What's the probability at least one shows up?
6. A ride-sharing app gets requests at a rate of 3/minute. What's the probability of 0 requests in a 2-minute window?
7. You roll two dice. Given that the sum is ≥ 9, what's the probability both dice show ≥ 4?
8. Users convert at 2%. You need 50 conversions for analysis. How many users do you expect to need?

## Hypothesis Testing

9. Explain p-value to a PM who has no statistics background.
10. What's the difference between one-tailed and two-tailed tests? When would you use each?
11. Your A/B test shows p = 0.06. What do you tell the PM? Ship or not?
12. Explain Type I and Type II errors using a product launch example.
13. How does sample size affect statistical power? Walk through the relationship.
14. You're running 10 A/B tests simultaneously. What's the problem and how do you fix it?
15. What's the difference between statistical significance and practical significance? Give an example.
16. When would you use a chi-squared test vs. a t-test vs. a z-test?

## Confidence Intervals & Estimation

17. Explain confidence intervals to a non-technical stakeholder. What does "95% CI" actually mean?
18. Your conversion rate is 5% with a 95% CI of [4.2%, 5.8%]. The PM asks if it's "really" 5%. What do you say?
19. How does confidence interval width change with sample size? With confidence level?
20. You want to estimate average order value within ±$2. How do you determine sample size?

## Distributions & Modeling

21. When would you use a Poisson distribution in a product context? Give 2 examples.
22. Revenue per user is heavily right-skewed. How does this affect your A/B test analysis?
23. Explain the Central Limit Theorem. Why does it matter for experimentation?
24. What distribution would you use to model time between user sessions? Why?
25. Your metric has extreme outliers. How do you handle this in analysis?

## Bayesian Thinking

26. Explain the difference between Bayesian and frequentist approaches to A/B testing.
27. When would you prefer a Bayesian approach over frequentist for experimentation?
28. Your prior belief is that a feature won't move the metric. The test shows a small positive result. How do you think about this?
29. Explain "credible interval" vs. "confidence interval" — what's the practical difference?
30. How would you use Bayesian methods to decide when to stop an experiment early?

---

## Tips for BIE → Product DS
- Don't just recite formulas — connect every concept to a product decision
- "This matters because..." should follow every statistical explanation
- Use real examples from your work: "At Amazon, we faced this when..."
- Show you understand the BUSINESS implication of statistical choices
- Interviewers care more about judgment than computation
