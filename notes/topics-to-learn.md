# Topics Still To Learn — Study Reference

These are the topics we haven't covered yet in practice sessions. Each includes the best resources I found for learning them in a digestible way.

---

## 1. Confidence Intervals

**What it is:** A range of values that likely contains the true population parameter. "The average order value is $50 ± $3 with 95% confidence."

**Why it matters in interviews:** "What does the 95% CI [3.2%, 6.8%] around your experiment result mean?" — comes up in every experimentation discussion.

**Best resources:**
- [Demystifying Confidence Intervals (Towards Data Science)](https://towardsdatascience.com/demystifying-confidence-intervals-with-examples-7bdef30f7b0a) — simple examples
- [How to Explain p-values and Confidence Intervals Clearly (bugfree.ai)](https://bugfree.ai/knowledge-hub/explain-p-values-confidence-intervals) — interview-focused
- [Simply Psychology — Confidence Intervals](https://www.simplypsychology.org/confidence-interval.html) — beginner-friendly

**Key interview trap:** 95% CI does NOT mean "95% probability the true value is in this range." It means "if we repeated this experiment 100 times, 95 of those intervals would contain the true value."

---

## 2. Power Analysis & Sample Size Calculation

**What it is:** Before an experiment, calculating how many users you need to detect a meaningful effect. The 4 inputs: baseline metric, MDE, alpha (0.05), power (0.80).

**Why it matters:** Every experiment design question includes "how long would you run it?" You need power analysis to answer.

**Best resources:**
- [Power Analysis Demystified (Medium/TDS)](https://medium.com/data-science/power-analysis-demystified-429b228b76b6) — derives the equation with a homepage signup example
- [Statsig — Calculating Sample Size](https://statsig.com/perspectives/ab-test-sample-size) — practical A/B test context
- [Evan Miller's A/B Test Calculator](https://www.evanmiller.org/ab-testing/sample-size.html) — play with it interactively

**Key relationships to memorize:**
- Smaller MDE → need more samples
- Higher power → need more samples
- Higher variance → need more samples
- The formula: N ≈ (Z_α + Z_β)² × 2σ² / δ² (don't memorize — understand the relationships)

---

## 3. Causal Inference: Difference-in-Differences (DiD)

**What it is:** Comparing changes over time between a treated and untreated group to estimate causal effects when you can't randomize.

**Analogy:** "Two runners — one gets new shoes, one doesn't. You don't just check who's faster after; you check how much EACH improved from their baseline." ([Statsig](https://statsig.com/perspectives/diff-in-diff-causal-inference))

**Why it matters:** Meta and Google test this directly. "You can't A/B test this. How do you measure the effect?"

**Best resources:**
- [Statsig — Difference-in-Differences Causal Inference](https://statsig.com/perspectives/diff-in-diff-causal-inference) — simple with product context
- [Understanding DiD: Finding Causality in the Real World (Medium)](https://patonv.medium.com/understanding-difference-in-differences-finding-causality-in-the-real-world-bdfc25ee8b18) — beginner friendly
- [The Effect Book — Ch 18 DiD](https://theeffectbook.net/ch-DifferenceinDifference.html) — comprehensive free textbook chapter
- [TheLinuxCode — Practical Guide for Product Teams](https://thelinuxcode.com/difference-in-differences-did-a-practical-guide-for-product-data-and-engineering-teams/) — product examples

**Key assumption:** Parallel trends — both groups would have followed the same trend WITHOUT the intervention.

---

## 4. Causal Inference: Regression Discontinuity Design (RDD)

**What it is:** Exploiting a threshold/cutoff to estimate causal effects. People just above and just below a cutoff are essentially identical — the only difference is the treatment.

**Analogy:** Scholarship for students scoring >80. Students who scored 79 vs. 81 are basically the same — comparing their outcomes estimates the scholarship's causal effect.

**Product example:** Amazon gives Prime trial to users spending >$100 in first month. Compare users at $99 vs. $101. ([freeCodeCamp — RDD with LLM confidence thresholds](https://www.freecodecamp.org/news/gen-ai-product-experimentation-with-regression-discontinuity-design/))

**Best resources:**
- [Regression Discontinuity Design: How It Works (TDS)](https://towardsdatascience.com/regression-discontinuity-design-how-it-works-and-when-to-use-it) — clear with examples
- [An Introduction to RDD (TDS)](https://towardsdatascience.com/an-introduction-to-regression-discontinuity-design-f55075079def) — beginner level
- [freeCodeCamp — RDD with LLM confidence thresholds](https://www.freecodecamp.org/news/gen-ai-product-experimentation-with-regression-discontinuity-design/) — modern AI product example

---

## 5. Distributions — When to Use Which

**What it is:** Knowing which probability distribution matches which real-world scenario.

**The cheat sheet:**

| Distribution | Use when | Product example |
|---|---|---|
| **Normal** | Continuous data, symmetric, large samples (CLT) | User heights, average order values |
| **Binomial** | Fixed number of trials, each with same probability | Conversion rate (N users, each converts or not) |
| **Poisson** | Events per time interval, rare and independent | Support tickets per hour, app crashes per day |
| **Exponential** | Time BETWEEN events | Time between user sessions, time between purchases |
| **Log-normal** | Right-skewed positive values | Revenue per user, session duration |

**Best resources:**
- [4 Probability Distributions Every DS Needs (Built In)](https://builtin.com/data-science/probability-distributions-data-science) — concise overview
- [Probability Distributions: Poisson vs Binomial (TDS)](https://towardsdatascience.com/probability-distributions-poisson-vs-binomial-distribution-ff8a6ddeb4a1/) — the most common interview comparison
- [Complete Guide (mbrenndoerfer.com)](http://mbrenndoerfer.com/writing/probability-distributions-guide-data-science) — interactive, choose your level

**Key interview question:** "Revenue per user is heavily right-skewed. How does this affect your A/B test?" → Use log-transformation or non-parametric tests. Mean is not representative; consider median or trimmed mean.

---

## 6. Cohort Analysis & Retention Curves

**What it is:** Grouping users by when they started (or what they did) and tracking each group over time to see retention patterns.

**Why it matters:** "How would you measure retention?" is asked at every FAANG company.

**Key insight:** Overall retention can look flat (30%) while hiding that old cohorts are dying and new cohorts are retaining at 45%. Cohort analysis separates these. ([OpenPanel](https://openpanel.dev/articles/cohort-analysis))

**What a healthy retention curve looks like:** Drops initially, then FLATTENS at a non-zero percentage. Flattening = product-market fit. Continuous decay to zero = leaky bucket.

**Best resources:**
- [OpenPanel — What Is Cohort Analysis](https://openpanel.dev/articles/cohort-analysis) — excellent plain-English explanation with the triangle grid visual
- [Mixpanel — Cohort Analysis in 2026](https://mixpanel.com/blog/what-is-cohort-analytics/) — modern with product context
- [KISSmetrics — How to Track User Groups](https://kissmetrics.io/blog/cohort-analysis-guide) — practical guide
- [Amplitude — Cohort Retention](https://amplitude.com/explore/analytics/cohort-retention-analysis) — good definitions

---

## 7. Funnel Analysis

**What it is:** Mapping a user's path through a multi-step flow and measuring drop-off at each step.

**Example:** Homepage → Product page → Add to cart → Checkout → Purchase. If 1000 users land and only 30 purchase, where are the biggest leaks?

**Why it matters:** "Where would you focus to improve conversion?" — funnel analysis gives the data-driven answer (fix the biggest drop-off first).

**Best resources:**
- [UXCam — Conversion Funnel Analysis](http://uxcam.com/blog/conversion-funnel-analysis/) — clear definition + examples
- [Product Compass — How to Track and Optimize](https://www.productcompass.pm/p/funnel-analysis) — product-focused
- [Quadratic — From Signup to Activation](https://www.quadratichq.com/blog/funnel-analysis-from-signup-to-activation-and-beyond) — step by step

**Interview pattern:** Decompose the funnel, calculate conversion rate between each step, identify the biggest absolute drop-off, hypothesize WHY, recommend a fix + how to test it.

---

## 8. Switchback Experiments

**What it is:** Instead of splitting users into treatment/control, you split TIME. The entire system alternates between treatment and control in time blocks (e.g., treatment for 2 hours, control for 2 hours, repeat).

**Why it's needed:** In marketplaces (Uber, DoorDash), user-level randomization doesn't work because supply is shared. If treatment riders get higher prices, freed-up drivers help control riders. SUTVA is violated.

**Best resources:**
- [Towards AI — Why A/B Testing Fails in Two-Sided Marketplaces](https://pub.towardsai.net/why-a-b-testing-fails-in-two-sided-marketplaces-and-how-to-fix-it-with-switchback-testing-12f14eb29700) — best explanation of WHY
- [Statsig — Switchback Experiments Overview](https://statsig.com/blog/switchback-experiments) — concise practical guide
- [TDS — How to Optimize Switchback Configuration](https://towardsdatascience.com/how-to-optimize-your-switchback-a-b-test-configuration-791a28bee678) — deeper dive
- [Bolt Labs — Tips for Switchback Designs](https://medium.com/bolt-labs/tips-and-considerations-for-switchback-test-designs-d1bd7c493024) — practical tips

**Trade-off:** Lower power (fewer independent time blocks than users), but eliminates interference. Used by Uber, Lyft, DoorDash, Bolt.

---

## 9. Long-Term Holdback Experiments

**What it is:** After shipping a feature, keep a small % of users (5-10%) permanently WITHOUT the feature as a control. Compare them to everyone else after 30/60/90 days to measure long-term effects.

**Why it matters:** Short-term A/B tests can't measure long-term effects (retention, LTV, habit formation). Holdbacks can.

**When to mention:** "How would you measure the long-term impact of this feature?" → "I'd run a long-term holdback — keep 5% of users without the feature and compare retention at 90 days."

**Trade-off:** Ethical concern (withholding a known-good feature), and small group means low power for subtle effects.

---

## 10. Behavioral Interviews (STAR Practice)

**What it is:** Telling structured stories about your past work experience using Situation → Task → Action → Result format.

**Why it matters:** Amazon dedicates 2-3 LPs per interviewer. Meta has a full behavioral round. Even technical rounds at Amazon test LPs.

**Your gap:** You haven't practiced any STAR stories yet. Need to build a bank of 8-10 stories from your BIE work.

**Best resources:** Already in your repo at `frameworks/star-method.md` and `questions/behavioral/README.md`

**Action needed:** Write out 8 stories covering: influence, conflict, ambiguity, failure, data-driven decisions, ownership, delivering results, customer focus.

---

## Priority Order for Learning

| # | Topic | Interview Frequency | Your Current Level | Learn By |
|---|-------|-------|---|---|
| 1 | Power Analysis | Every experiment question | 🟡 Vague | Week 2 |
| 2 | Confidence Intervals | Every stats discussion | ❓ Untested | Week 2 |
| 3 | Cohort Analysis / Retention | High at all companies | ❓ Untested | Week 3 |
| 4 | Funnel Analysis | High for product sense | ❓ Untested | Week 3 |
| 5 | Diff-in-Diff | High at Meta/Google | ❓ Taught briefly | Week 4 |
| 6 | Distributions | Medium | ❓ Untested | Week 4 |
| 7 | Regression Discontinuity | Medium at Meta/Google | ❓ Untested | Week 5 |
| 8 | Switchback Experiments | Medium (marketplace roles) | ❓ Untested | Week 5 |
| 9 | Behavioral STAR | High at all companies | ❌ Not practiced | Start NOW |
| 10 | Long-term Holdbacks | Low-medium | ❓ Untested | Week 6 |
