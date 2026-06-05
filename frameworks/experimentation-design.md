# Experiment Design Framework

Use this when asked: "How would you design an A/B test for X?" or "How would you validate this?"

---

## End-to-End Experiment Design (7 Steps)

### 1. DEFINE the hypothesis
- What change are we making? (treatment)
- What do we expect to happen? (directional hypothesis)
- Why do we believe this? (theory/prior evidence)

Example: "Adding a progress bar to checkout will increase completion rate because users feel less uncertain about remaining steps."

### 2. CHOOSE metrics
- **Primary metric (OEC)**: The ONE metric that determines success
- **Secondary metrics**: Supporting signals (2–3 max)
- **Guardrail metrics**: What must NOT degrade (revenue, latency, satisfaction)

### 3. DETERMINE the unit of randomization
- User-level (most common)
- Session-level (when user identity is unavailable)
- Geo-level (when network effects exist)
- Device-level (cross-platform considerations)

Ask: "Can one user's treatment affect another user's outcome?" If yes → user-level won't work.

### 4. CALCULATE sample size & duration
Inputs needed:
- Baseline metric value
- Minimum Detectable Effect (MDE) — smallest change worth detecting
- Significance level (α, typically 0.05)
- Power (1-β, typically 0.80)
- Traffic available per day

Formula intuition: Smaller MDE → need more samples. Higher power → need more samples.

Duration considerations:
- Minimum: enough for statistical power
- Account for day-of-week effects (run full weeks)
- Account for novelty/primacy effects (run ≥2 weeks)
- Don't run too long (opportunity cost, external changes)

### 5. DESIGN the experiment
- Control: existing experience (no change)
- Treatment: new experience (one change only)
- Split ratio: typically 50/50 (maximize power)
- Ramp plan: start at 5% → 50% if no guardrail violations

### 6. RUN & MONITOR
- Pre-check: verify randomization balance (covariate check)
- Monitor guardrail metrics daily
- Do NOT peek at primary metric repeatedly (inflates false positive rate)
- If using sequential testing, define stopping rules upfront

### 7. ANALYZE & DECIDE
- Check statistical significance of primary metric
- Check practical significance (is the effect size meaningful?)
- Check guardrail metrics (any degradation?)
- Segment analysis: does it work for all users or just some?
- Decision: Ship / Iterate / Kill

---

## When You CAN'T A/B Test

| Situation | Alternative Method |
|-----------|-------------------|
| Network effects (social, marketplace) | Geo/cluster randomization, switchback design |
| Small user base | Bayesian methods, longer duration |
| Irreversible changes (pricing, brand) | Quasi-experiments, holdout groups |
| Ethical concerns | Observational study + causal inference |
| Long-term effects | Holdback experiments, cohort analysis |
| Supply-side changes (marketplace) | Switchback experiments, synthetic control |

### Causal Inference Methods (when no experiment possible)
- **Difference-in-differences**: Compare before/after across treated vs. control groups
- **Regression discontinuity**: Exploit a threshold (e.g., users above/below a score)
- **Instrumental variables**: Find an exogenous source of variation
- **Propensity score matching**: Match treated/control on observables
- **Synthetic control**: Construct a counterfactual from weighted combination of controls

---

## Key Concepts from "Trustworthy Online Controlled Experiments"

| Concept | What It Means | When to Mention |
|---------|--------------|-----------------|
| OEC | Single metric capturing experiment success | Metric selection |
| Twyman's Law | Surprising results are usually data bugs | Before celebrating results |
| Intention-to-treat | Analyze by assignment, not by usage | Experiment analysis |
| SUTVA | One user's treatment doesn't affect others | Randomization unit choice |
| Novelty effect | Users react to newness, not the feature | Duration decisions |
| Primacy effect | Users resist change initially | Duration decisions |
| Guardrail metrics | Metrics that must not degrade | Experiment design |
| Variance reduction (CUPED) | Use pre-experiment data to reduce noise | Power/sensitivity |

---

## Example

> "How would you test whether a new recommendation algorithm improves engagement?"

**Hypothesis**: New algo surfaces more relevant content → users engage more.

**Metrics**:
- OEC: Sessions per user per week (engagement frequency)
- Secondary: Time spent, content diversity consumed
- Guardrails: Revenue per user, app crashes, creator content views (don't starve long-tail)

**Randomization**: User-level (recommendations are personalized, low interference)

**Sample size**: Baseline 4.2 sessions/week, MDE 2% (0.084 sessions), α=0.05, power=0.80 → ~150K users per group

**Design**: 50/50 split, ramp from 5% → 50% over 3 days, run for 3 weeks (full weekly cycles + novelty buffer)

**Analysis**: After 3 weeks, check OEC significance. Segment by user tenure (new vs. power users). Check if algo helps across content types or just popular content.
