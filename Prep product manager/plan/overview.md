# 12-Week Product Data Scientist Interview Prep Plan

## Profile
- Current role: BIE at Amazon
- Target: L5 Product Data Scientist (FAANG — internal + external)
- Timeline: ~3 months
- Strengths: SQL, data pipelines, dashboards, Weblab/experimentation exposure
- Growth areas: Statistics depth, causal inference, Python for DS, product sense framing
- Key resource: "Trustworthy Online Controlled Experiments" (Kohavi, Tang, Xu)

## Target Companies & Titles
| Company | Title | Notes |
|---------|-------|-------|
| Meta | Product Data Scientist, Analytics | 45% product sense weight |
| Google | Data Scientist / Quantitative Analyst | Hiring committee decides |
| Amazon | Data Scientist (internal transfer) | LP-heavy, experiment design |
| Netflix | Data Scientist | Experimentation-first culture |
| Apple | Data Scientist | |

---

## Interview Format (Typical Product DS Loop)

| Round | What's Tested | Time |
|-------|--------------|------|
| SQL | Window functions, CTEs, complex joins, optimization | 45 min |
| Statistics & Experimentation | Hypothesis testing, A/B design, power, pitfalls | 45 min |
| Product Sense / Metrics | Metric definition, diagnosis, trade-offs | 45 min |
| Behavioral | Leadership, influence, conflict (STAR format) | 45 min |
| Coding (sometimes) | Python — pandas, data manipulation, light modeling | 45 min |

---

## Philosophy
- **Weeks 1–4:** Build foundations — statistics, experimentation, product metrics
- **Weeks 5–8:** Deep practice — timed problems, mock interviews, case studies
- **Weeks 9–12:** Sharpen — full mock loops, company-specific prep, weak spots

---

## Phase 1: Foundations (Weeks 1–4)

### Week 1 — Statistics & Probability Refresh
- [ ] Review: distributions (normal, binomial, Poisson), CLT, law of large numbers
- [ ] Review: confidence intervals, p-values, hypothesis testing mechanics
- [ ] Review: Type I / Type II errors, power, significance level
- [ ] Practice: 5 probability problems (conditional probability, Bayes' theorem)
- [ ] SQL practice: 3 LeetCode problems (medium — window functions)
- [ ] Start "Trustworthy Online Controlled Experiments" — Ch 1–2

### Week 2 — Experimentation Foundations
- [ ] Study: A/B test design end-to-end (randomization, sample size, duration)
- [ ] Study: OEC (Overall Evaluation Criterion) and guardrail metrics
- [ ] Study: Common pitfalls — novelty effect, peeking, Simpson's paradox
- [ ] Practice: "Design an A/B test for X" — 2 questions
- [ ] SQL practice: 3 LeetCode problems (medium — CTEs, subqueries)
- [ ] Continue book — Ch 3–5 (Twyman's Law, Speed Matters)

### Week 3 — Product Metrics & Sense
- [ ] Learn: AARRR funnel, North Star metrics, metric trees
- [ ] Learn: How to decompose a metric drop (segmentation, time, cohort)
- [ ] Practice: "How would you measure success for X?" — 3 questions
- [ ] Practice: "Metric X dropped 15%. Diagnose it." — 2 questions
- [ ] SQL practice: 3 LeetCode problems (medium/hard)
- [ ] Continue book — Ch 7 (Metrics)

### Week 4 — Behavioral Stories + Causal Inference Intro
- [ ] Build STAR story bank (8–10 stories covering Amazon LPs)
- [ ] Map stories to themes: data-driven decisions, influence, ambiguity, failure
- [ ] Study: Causal inference basics — observational vs. experimental, confounders
- [ ] Study: Difference-in-differences, regression discontinuity (high-level)
- [ ] Practice: 3 behavioral questions with Kiro
- [ ] SQL practice: 3 LeetCode problems (hard)
- [ ] Continue book — Ch 11 (Observational Studies)

---

## Phase 2: Deep Practice (Weeks 5–8)

### Week 5 — Experimentation Deep Dive
- [ ] Study: Power analysis, minimum detectable effect, sample size calculation
- [ ] Study: Multiple testing correction (Bonferroni, FDR)
- [ ] Study: Network effects and interference — when user-level randomization fails
- [ ] Practice: 4 experimentation questions (timed 15 min each)
- [ ] Mock session with Kiro: 1 full experimentation round
- [ ] SQL practice: 2 LeetCode problems (hard)
- [ ] Book — Ch 17 (Pitfalls), Ch 19 (Organizational)

### Week 6 — Product Sense & Metrics Deep Dive
- [ ] Practice: "Define metrics for [product]" — 3 questions (timed 20 min)
- [ ] Practice: "Metric dropped" root cause — 3 scenarios (timed 15 min)
- [ ] Practice: Trade-off questions — "engagement up, satisfaction down" — 2 questions
- [ ] Mock session with Kiro: 1 full product sense round
- [ ] SQL practice: 2 LeetCode problems (hard)
- [ ] Python practice: pandas data manipulation — 2 exercises

### Week 7 — Statistics & Probability Deep Dive
- [ ] Practice: 8 statistics questions (hypothesis testing, CI, Bayesian)
- [ ] Practice: 5 probability problems (medium/hard)
- [ ] Study: Bayesian vs. frequentist approaches to experimentation
- [ ] Study: Bootstrap methods, permutation tests
- [ ] Mock session with Kiro: 1 statistics round
- [ ] SQL practice: 2 LeetCode problems (hard)
- [ ] Python practice: statistical analysis with scipy/statsmodels — 2 exercises

### Week 8 — Python Coding & Causal Inference
- [ ] Practice: Python data manipulation (pandas, numpy) — 4 problems
- [ ] Practice: Write A/B test analysis in Python (power calc, significance test)
- [ ] Study: Instrumental variables, propensity score matching (conceptual)
- [ ] Practice: "You can't A/B test this. What do you do?" — 3 questions
- [ ] Mock session with Kiro: 1 coding round
- [ ] SQL practice: 2 LeetCode problems (hard)

---

## Phase 3: Sharpen & Simulate (Weeks 9–12)

### Week 9 — Full Mock Loops
- [ ] Simulate full interview with Kiro: SQL + Stats + Product Sense + Behavioral
- [ ] Identify top 2 weak areas from mock
- [ ] Targeted practice on weak areas: 4 questions each
- [ ] SQL practice: 2 LeetCode problems (hard)

### Week 10 — Company-Specific Prep
- [ ] Research target companies: what their DS teams work on, recent blog posts
- [ ] Prepare "Why DS? Why this company?" narrative
- [ ] Meta-specific: practice product sense with business acumen angle (45% weight)
- [ ] Amazon-specific: practice LP stories with data/experimentation examples
- [ ] Google-specific: practice quantitative reasoning under ambiguity
- [ ] SQL practice: 2 LeetCode problems (hard)

### Week 11 — Refinement
- [ ] Re-do weakest 5 questions from entire prep
- [ ] Polish STAR stories — final versions with quantified results
- [ ] Full mock with Kiro: simulate interviewer pushback and follow-ups
- [ ] Practice explaining technical concepts simply (for cross-functional communication)
- [ ] SQL practice: review missed problems

### Week 12 — Final Prep & Confidence
- [ ] Light review: statistics cheat sheet, experimentation concepts, metric frameworks
- [ ] 1 final full mock loop with Kiro
- [ ] Prepare questions to ask interviewers
- [ ] Review "Trustworthy Online Controlled Experiments" key concepts one more time
- [ ] Rest and mental prep

---

## Weekly Rhythm (Suggested)
| Day | Focus | Time |
|-----|-------|------|
| Mon | Statistics / experimentation study | 45–60 min |
| Tue | Practice questions (timed) | 45–60 min |
| Wed | SQL on LeetCode | 30–45 min |
| Thu | Mock session with Kiro OR Python practice | 45–60 min |
| Fri | Product sense / metrics practice | 30–45 min |
| Sat | Book reading + case study (optional) | 45–60 min |
| Sun | Rest or light review | — |

---

## Progress Tracking
Update checkboxes as you complete items. After each week, note:
- What went well
- What needs more work
- Confidence level (1–5) per category:
  - [ ] SQL: _/5
  - [ ] Statistics: _/5
  - [ ] Experimentation: _/5
  - [ ] Product Sense: _/5
  - [ ] Behavioral: _/5
  - [ ] Python: _/5
