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

### 2026-06-10 | Statistics/Probability | Bayes' Theorem — RESOLVED ✅
**Progress:** Previously marked as "does not know how to apply." Today solved a Bayes problem correctly on first attempt using the concrete numbers method (100 people → split → apply rates → count → divide). Got 4/13 ≈ 30.8% correct.
**Status:** Practicing more problems to solidify. Moving from "learned" to "automatic."

### 2026-06-10 | Statistics/Probability | Bayes' Theorem — arithmetic error in concrete numbers method
**What was wrong:** Got the right approach (split → apply rates → count → divide) but wrong numbers. Said "9+4" and "9/13" without showing the full breakdown. With 1,000 emails: 100 spam, 900 legit. Spam flagged: 90% × 100 = 90 (not 9). Legit flagged: 5% × 900 = 45 (not 4). Total flagged: 90 + 45 = 135. Probability = 90/135 = 66.7% (not 9/13).
**Root cause:** Used 100 total instead of 1,000, or forgot to scale the percentages correctly. Possibly rushed and divided by 10 mentally.
**Key lesson:** Always write out the full breakdown explicitly: (1) state population size, (2) split into groups with actual numbers, (3) apply rates showing multiplication, (4) then divide. Don't shortcut the arithmetic.

### 2026-06-10 | Statistics + Product | Bayes → Product Recommendation — good direction but missing actionable alternatives
**What was good:** ✅ Correctly identified the problem (86% of bans would hit real users). ✅ Made a clear recommendation (don't auto-ban). ✅ Connected the math to business impact. This is a real improvement on the "connect stats to business" gap.
**What was missing:** The answer says what NOT to do, but doesn't say what TO do instead. A strong interview answer proposes alternatives:
1. Use a confidence threshold — only auto-ban accounts above 95% probability (add more signals)
2. Tiered response — high-confidence flags → auto-ban, medium → restrict features + human review, low → monitor
3. Add more signals to the model — account age, posting patterns, friend count — to reduce false positives
4. Use the flag as a trigger for CAPTCHA or phone verification instead of outright ban

**Key lesson:** When recommending AGAINST something, always propose what you'd do INSTEAD. "Don't do X" is half an answer. "Don't do X, instead do Y because Z" is a complete recommendation.

### 2026-06-10 | Product Sense | Metric diagnosis — strong structure, minor gaps remain
**What was good:** ✅ Stated structure upfront. ✅ Verified data first. ✅ Segmented (region, time of day). ✅ Multi-sided thinking (drivers, restaurants, customers). ✅ Decomposed the pipeline. ✅ Checked timeline. Major improvement from earlier sessions.
**What was missing/slightly off:**
1. **Hypothesis testing is unnecessary here** — this isn't an A/B test. An 18% increase over 3 days vs. prior week is clearly real (not random noise) at DoorDash's scale. Setting up a formal hypothesis test adds confusion. In diagnosis questions, the metric change is assumed real — your job is to find WHY, not prove IF.
2. **No concrete hypotheses listed** — said "I'll find the root cause" but didn't propose specific hypotheses. A strong answer lists 3-4 ranked hypotheses: (a) driver shortage due to a competing app's bonus, (b) weather events in key markets, (c) restaurant prep time increase due to understaffing, (d) routing algorithm change deployed recently.
3. **No recommendation** — didn't end with "based on what I find, I'd recommend X" or "if the root cause is Y, then we should Z."
4. **Decomposition could be more specific** — Delivery time = Dispatch time + Driver travel to restaurant + Restaurant prep time + Driver travel to customer. Naming these specific stages is stronger than saying "which part of the pipeline."

**Key lesson:** In diagnosis questions, skip hypothesis testing (the change is real). Instead: list 3-4 specific hypotheses ranked by likelihood, and always end with a recommendation.

### 2026-06-10 | Experimentation | CUPED — partial understanding, missing the core WHY
**What was partially right:** Understands that pre-experiment data gives you a before/after comparison.
**What was wrong/missing:** The explanation confuses CUPED with a simple pre/post comparison. CUPED is NOT just "compare before vs. after." The core insight is about VARIANCE REDUCTION:
- Without CUPED: Users vary wildly (heavy spender vs. light spender). This natural variation makes it hard to detect a small treatment effect — it's buried in the noise between users.
- With CUPED: By knowing each user's BASELINE behavior, you can "subtract out" the predictable part of their behavior. What remains is ONLY the variation caused by the experiment. Less noise → smaller effects become detectable → you need fewer users or less time.
- It's like noise-canceling headphones: the pre-experiment data tells you the "background noise" for each user, and CUPED removes it so you can hear the "signal" (treatment effect) more clearly.
- Important: CUPED still compares treatment vs. control (not pre vs. post). It just uses pre-experiment data to make that comparison less noisy.

**Key lesson:** CUPED reduces VARIANCE (noise between users), which increases POWER (ability to detect effects). It's not about pre/post comparison — it's about removing predictable user-level noise so the treatment effect stands out.

### 2026-06-10 | Statistics | Simpson's Paradox — LEARNED ✅
**Status:** Explained the concept, then gave a quiz scenario. Alok correctly identified the mix shift (mobile → desktop) causing the paradox. Used the right language ("mix shifted"). No gap here — understood on first try.

### 2026-06-10 | Experimentation | CUPED — PARTIALLY LEARNED 🟡
**Status:** Initially confused CUPED with a simple pre/post comparison. After correction, understood the core idea: "adjust each user by their baseline, then compare the residuals across treatment vs. control." Understands the intuition (variance reduction) but may need reinforcement with a practice problem later.

### 2026-06-10 | Experimentation | Diagnosis — don't hypothesis-test a known metric change
**Gap:** Applied hypothesis testing logic to a diagnosis question (18% delivery time increase). In diagnosis questions, the change is assumed real — the job is to find WHY, not prove IF.
**Key lesson:** Hypothesis testing is for experiments. Diagnosis questions skip straight to: decompose → segment → hypothesize causes → validate → recommend.

### 2026-06-10 | Product Sense | "Don't do X" without proposing alternatives
**Gap:** In the Bayes bot-detection follow-up, correctly said "don't auto-ban" but didn't propose what to do instead.
**Key lesson:** When pushing back on a PM's proposal, always offer alternatives (tiered response, confidence threshold, additional signals).

---

## Updated Patterns & Focus Areas (2026-06-10)
- **Bayes' theorem:** ✅ RESOLVED — can solve with concrete numbers method
- **Simpson's Paradox:** ✅ Learned — got it on first try
- **CUPED:** 🟡 Conceptually understood, needs reinforcement
- **Structure:** ✅ Now automatic — states framework upfront every time
- **Multi-sided thinking:** ✅ Improved — naturally considers multiple user groups
- **Specific hypotheses in diagnosis:** 🟡 Still vague — needs to name 3-4 concrete causes
- **Metric decomposition:** 🟡 Self-identified gap — needs practice writing equations
- **"What TO do" not just "what NOT to do":** 🟡 New pattern to build
- **Don't hypothesis-test diagnosis problems:** 🟡 New lesson
- **Connecting stats to business impact:** Improving

### 2026-06-10 | Experimentation | Multiple Testing / p-hacking — LEARNED ✅
**Status:** Understood the concept immediately. When quizzed (PM found effect in narrow segment), correctly identified it as likely p-hacking, mentioned Bonferroni correction, and recommended follow-up experiment. Used right reasoning. No gap.

### 2026-06-10 | Experimentation | Novelty Effect & Primacy Effect — LEARNING 🟡
**Status:** Concept taught. Not yet quizzed. Awaiting answer to the Spotify question (Week 1: +12%, Week 2: +6%, Week 3-4: +5%).

---

## Reinforce Next Session (quiz on these — learned but not yet solidified)
- [ ] CUPED — ask a scenario where they need to reduce experiment duration
- [ ] Simpson's Paradox — give a product scenario and ask them to identify the paradox
- [ ] Multiple Testing — ask what they'd do with 5 metrics showing mixed results
- [ ] Novelty vs. Primacy — give week-over-week data, ask to interpret (pending from today)

### 2026-06-10 | Experimentation | Novelty vs. Primacy Effect — LEARNED ✅
**Status:** Correctly identified novelty effect in Spotify scenario, found the true stable effect (+5%), and made a recommendation with trade-off reasoning.

### 2026-06-10 | Experimentation | Intention-to-Treat (ITT) — LEARNED ✅
**Status:** Needed ELI5 explanation to grasp the concept initially. Once understood, correctly explained why only analyzing adopters introduces selection bias, and that diluted-but-unbiased is better than strong-but-biased. Interview-ready.

---

## Session Summary — 2026-06-10

**Duration:** ~1 hour
**Concepts learned:** 6 (Bayes reinforced, CUPED, Simpson's Paradox, Multiple Testing, Novelty/Primacy, ITT)
**Practice questions:** 4 (Bayes ×3, DoorDash diagnosis, Novelty quiz, ITT quiz)
**Gaps found:** Diagnosis still needs specific hypotheses + metric decomposition equations. CUPED partially understood.
**Wins:** Bayes is now solid. Structure habit maintained after 1 week off. Multi-sided thinking is natural. Making recommendations consistently.

## Reinforce Next Session (quiz on these — learned but not yet solidified)
- [ ] CUPED — ask a scenario where they need to reduce experiment duration
- [ ] Simpson's Paradox — give a product scenario and ask them to identify the paradox
- [ ] Multiple Testing — ask what they'd do with 5 metrics showing mixed results
- [ ] Novelty vs. Primacy — give week-over-week data, ask to interpret
- [ ] ITT — give a scenario with low adoption rate, ask how to analyze
- [ ] Metric decomposition — give a product metric and ask them to write the equation

### 2026-06-17 | Experimentation | CUPED reinforcement — forgot the concept, gave generic answer
**What was wrong:** When asked how to get experiment results in 2 weeks instead of 4, answered "increase the number of test users." That's a valid generic answer but NOT CUPED. The question was specifically testing whether CUPED was retained. Increasing traffic is the brute-force option. CUPED is the smart option — it reduces variance using pre-experiment data, effectively giving you the same power with less data/time.
**Expected answer:** "I'd apply CUPED — use each user's pre-experiment behavior to reduce variance in the metric. This can reduce required sample size by 30-50%, cutting experiment duration roughly in half without needing more traffic."
**Key lesson:** CUPED needs more practice. Remember: CUPED = variance reduction = noise-canceling headphones for your experiment. It lets you detect the same effect with fewer users/less time.

### 2026-06-17 | Experimentation | Multiple testing — good reasoning, missed explaining WHY secondaries are unreliable
**What was good:** ✅ Correctly said OEC is what matters and feature shouldn't ship. ✅ Suggested follow-up experiment for secondary metric interest.
**What was missing:** Didn't explain WHY the 2 significant secondary metrics are likely false positives. The full answer should include: "With 5 secondary metrics at alpha=0.05, we'd expect ~1 false positive by chance alone. Seeing 2 'significant' results is barely above the expected noise. I'd apply Bonferroni correction (p < 0.05/5 = 0.01) — likely neither would pass."
**Key lesson:** When discussing multiple testing, always state the math: "With N tests at 5%, we expect N×0.05 false positives by chance." Then mention correction method.

### 2026-06-17 | Product Sense | Metric decomposition — thinking like an accountant, not a product DS
**What was wrong:** Decomposed Uber revenue as a P&L statement (revenue - driver costs - overhead × 12). This is a FINANCE decomposition, not a PRODUCT decomposition. A Product DS doesn't think about costs and office buildings — they think about user behavior that DRIVES the top-line metric.
**What was expected:** A product decomposition breaks the metric into user-behavior components that a product team can influence:
- Uber Revenue = Active Riders × Rides per Rider × Average Fare per Ride
- Or even deeper: Revenue = Riders × Sessions per Rider × Conversion Rate (session → ride) × Avg Fare
- Or: Revenue = Rides Completed × Avg Fare = (Requests × Match Rate × Completion Rate) × Avg Fare
**Why this matters:** When revenue drops, the product team asks "which lever broke?" They can't fix "office costs" — but they CAN fix conversion rate, or match rate, or rider retention. The decomposition tells you WHERE to investigate and WHAT to improve.
**Key lesson:** Product metric decomposition = breaking a metric into USER BEHAVIOR components that a product team can influence. Not accounting/finance components. Think: "What user actions multiply together to produce this number?"

### 2026-06-17 | Combo Question | Netflix "Play Something" — mixed results

**Q1 Simpson's Paradox — ❌ Incorrect identification:**
Said "yes" because segments showed different behavior. But this is NOT Simpson's Paradox. Simpson's is when the overall trend REVERSES in segments (overall positive but negative in ALL segments). Here, overall is +4%, new users are +11%, returning users are -1%. The overall direction matches the dominant segment (new users drove the lift). This is just a segment-level difference — new users benefit more. Not a paradox.
**Key distinction:** Simpson's = overall trend CONTRADICTS all segment trends. This scenario = overall trend is driven disproportionately by one segment (new users). Different thing.

**Q2 ITT (Intention-to-Treat) — ❌ Skipped / didn't know:**
Left blank. The concept: only 22% clicked the button, but you analyze ALL 100% of assigned users (ITT principle). The reported +4% is already diluted. For adopters, the estimated effect is +4%/0.22 ≈ +18%. Report both: "ITT is +4%, estimated effect for users who engage is ~18%."

**Q3 Novelty Effect — ✅ Correct:**
Correctly identified weekly decay as novelty effect.

**Q4 Recommendation — 🟡 Partial:**
Said "iterate and wait" which is reasonable. But missed: (1) The stable effect is ~3% (week 3 plateau), not 4%. (2) Should mention that it primarily helps NEW users — could ship only to new users or investigate why returning users don't benefit. (3) Didn't propose alternatives (ship to new users only? redesign for returning users?).

**Key lessons:**
- Simpson's Paradox ≠ "segments are different." It specifically means the overall trend REVERSES in every segment.
- ITT needs to be automatic: if adoption < 100%, mention "ITT effect is X%, per-adopter effect is approximately X/adoption_rate."
- Recommendations should be specific: WHO to ship to, and propose alternatives when results are mixed.

### 2026-06-17 | Product Sense | Metric definition — "Buy Again" — improving but North Star still measures activity not value
**What was good:** ✅ Started with goal. ✅ Stated structure. ✅ Supporting metrics tell different stories (orders + time). ✅ Guardrails are specific and thoughtful (cancellations from accidental orders, cannibalization of new product discovery). The cannibalization guardrail is especially strong — shows product maturity.
**What needs improvement:**
1. **Goal could be sharper** — "Increase number of products ordered" is okay but surface-level. Sharper: "Reduce friction for repeat purchases, increasing purchase frequency and customer retention." This connects to WHY Amazon benefits (LTV, not just order count).
2. **North Star measures ACTIVITY not VALUE** — "Number of products ordered through Buy Again" is an adoption/usage metric. It goes up even if people just click by accident. Better: "Weekly repurchase rate among users exposed to Buy Again" — this captures that people are actually building a repeat-buying habit, not just clicking once.
3. **Supporting metrics should include RETENTION** — The real value of Buy Again is it builds HABITS. If customers come back more often because reordering is easy, that's the true win. Add: "D30 return rate for Buy Again users vs. non-users" or "Monthly purchase frequency."
4. **Missing: incremental orders vs. cannibalization** — Are Buy Again orders NET NEW or just orders that would have happened anyway through search? Key supporting metric: "Did total orders increase, or did Buy Again just shift WHERE people click?" This is the incrementality question.

**Key lesson:** For features that reduce friction (Buy Again, one-click ordering, saved addresses), the real value is in HABIT formation and RETENTION, not just "did they use the feature." Ask: "Does this feature make customers come back more often?"
