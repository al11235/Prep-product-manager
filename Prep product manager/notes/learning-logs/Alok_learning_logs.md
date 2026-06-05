# Learning Log — Alok

This file tracks concepts Alok got wrong, didn't know, or needs more practice on.

---

## Gaps Identified

### 2026-05-27 | Statistics | Incomplete A/B test ship decision
**What was missing:** Correctly defined p-value but gave an incomplete answer to "should we ship?" Need to go beyond statistical significance and also discuss: practical significance, guardrail metrics, segment analysis, novelty effect, trade-offs.
**Key lesson:** "Statistically significant" ≠ "ship it." Always check: practical significance, guardrails, segments, and trade-offs before recommending a launch.

### 2026-05-27 | Product Sense | Metric definition — weak North Star choice & missing structure
**What was missing/wrong:** North Star too shallow (adoption metric, not value metric). No clarification of goal first. Supporting metrics overlapped. Missing retention metric.
**Key lesson:** A strong metric answer follows: (1) Clarify the goal, (2) Pick a North Star that captures VALUE not just usage, (3) Pick supporting metrics that each tell a different story, (4) Guardrails should protect against cannibalization and user experience degradation.

### 2026-05-27 | Product Sense | Metric diagnosis — good instincts but missing segmentation and supply-side thinking
**What was missing:** No segmentation by geography/platform/user type. Missed supply side (two-sided marketplace). No metric decomposition. No mention of app releases/deployments.
**Key lesson:** For marketplace products, always think about BOTH sides (supply + demand). Always decompose the metric into its components before hypothesizing. Always segment early.

### 2026-05-27 | Experimentation | Experiment design — missed key reason for A/B test and lacked specificity
**What was missing/wrong:** Missed the MAIN reason to A/B test (causal isolation from confounders). No specific metrics named. No randomization unit. No duration. No hypothesis stated.
**Key lesson:** The #1 reason to A/B test is to ISOLATE the causal effect with a simultaneous control group. Always state: hypothesis, primary metric, randomization unit, duration, and guardrails explicitly.

### 2026-05-28 | Product Sense | Metric definition — improving structure but still thinking one-sided
**What was missing:** Only thought about one user group. North Star too narrow. Goal could be sharper. Guardrail too generic. Missing creator-side metrics.
**Key lesson:** For features that affect multiple user groups, always measure success for EACH group separately.

### 2026-05-28 | Statistics | Alpha/power trade-off — correct direction but incomplete
**What was correct:** Identified that stricter alpha + higher power requires more data.
**What was missing:** Only mentioned sample size. Didn't connect to business impact: longer duration, opportunity cost, slower iteration, diminishing returns.
**Key lesson:** When asked about trade-offs, always connect the statistical concept to the BUSINESS impact.

### 2026-05-29 | Product Sense | Conflicting metrics — strong investigation but missing recommendation and ecosystem thinking
**What was good:** Verified data, segmented, formed hypothesis, proposed validation.
**What was missing:** No clear recommendation (ship/kill/iterate). Missed creator ecosystem concern. Didn't address the satisfaction score signal. Missing short-term vs. long-term framing.
**Key lesson:** For conflicting metrics, always: explain the mechanism, consider short-term vs. long-term, think about ecosystem effects, MAKE A RECOMMENDATION.

### 2026-05-29 | Statistics/Probability | Bayes' Theorem — does not know how to apply
**Gap:** Does not know how to solve Bayes' theorem / conditional probability problems.
**Priority:** High — this comes up frequently in DS interviews at all FAANG companies.

---

## Patterns & Focus Areas
- **Structure:** Improving — now states framework upfront consistently
- **Multi-sided thinking:** Was a gap, improving after targeted practice
- **Recommendations:** Getting better — committed in latest answers
- **Statistical vocabulary:** Needs work (SUTVA, MDE, OEC)
- **Bayes' theorem:** Needs to learn from scratch
- **Connecting stats to business impact:** Consistent gap
