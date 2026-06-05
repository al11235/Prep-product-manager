# Learning Log — Gaps & Concepts to Revisit

This file tracks concepts you got wrong, didn't know, or need more practice on.
Kiro updates this automatically during practice sessions.

---

## How This Works
- When you answer incorrectly or say "I don't know," the concept gets logged here
- Each entry includes: the topic, what you got wrong, and the correct explanation
- Review this file weekly to see patterns in your gaps
- Once you're confident on a concept, mark it ✅

---

## Gaps Identified

(entries will be added as we practice)

---

## Patterns & Focus Areas

(will be updated as gaps accumulate — e.g., "struggling with conditional probability" or "metric diagnosis is strong but experiment design needs work")

### 2026-05-27 | Statistics | Incomplete A/B test ship decision
**What was missing:** User correctly defined p-value but gave an incomplete answer to "should we ship?" In an interview, you need to go beyond statistical significance and also discuss:
1. **Practical significance** — Is a 0.3pp lift (4.2% → 4.5%) meaningful for the business? What's the revenue impact?
2. **Guardrail metrics** — Did anything get WORSE? (page load time, purchase rate, revenue per user)
3. **Segment analysis** — Does it help all users equally or just some?
4. **Novelty effect** — 2 weeks is okay but worth mentioning
5. **Trade-offs** — Any engineering/maintenance cost to keep the widget?

**Key lesson:** "Statistically significant" ≠ "ship it." Always check: practical significance, guardrails, segments, and trade-offs before recommending a launch.

### 2026-05-27 | Product Sense | Metric definition — weak North Star choice & missing structure
**What was missing/wrong:**
1. **North Star too shallow** — "Number of people listening to it" is an adoption metric, not a success metric. It tells you people tried it, not that they got value from it. A user who listens for 10 seconds and leaves counts the same as one who listens for 30 minutes. Better: "% of AI DJ sessions where user listens for 10+ minutes" or "D7 retention of AI DJ users" — these capture ongoing value, not just trial.
2. **No clarification of what "success" means** — Before picking metrics, a strong answer first asks: "What's the goal of this feature? Engagement? Retention? Acquisition?" Then picks metrics aligned to that goal.
3. **Supporting metrics overlap** — "mins listened," "overall listening time," and "time spent on app" are essentially the same thing measured at different scopes. Better to pick metrics that tell DIFFERENT stories (engagement depth, retention, content quality).
4. **Guardrail about "dropping after listening to radio"** — this is actually a good instinct (cannibalization) but wasn't articulated clearly. The concern is: does AI DJ cannibalize artist/album listening? Does it reduce music discovery diversity?
5. **Missing: retention metric** — The most important signal for a new feature is whether people come back to use it again (D7, D30 return rate).

**Key lesson:** A strong metric answer follows: (1) Clarify the goal, (2) Pick a North Star that captures VALUE not just usage, (3) Pick supporting metrics that each tell a different story, (4) Guardrails should protect against cannibalization and user experience degradation.

### 2026-05-27 | Product Sense | Metric diagnosis — good instincts but missing segmentation and supply-side thinking
**What was good:** Correctly started with data quality check (step 1), thought about external events (step 3). Good foundation.
**What was missing:**
1. **No segmentation** — Didn't break down by geography, platform (iOS/Android), user type (new/returning), ride type (UberX/Pool/Eats). This is the most powerful diagnostic step. "Is it all cities or just 3 cities?" narrows the investigation immediately.
2. **Missed supply side** — Uber is a two-sided marketplace. Ride completions can drop because of DEMAND issues (fewer riders requesting) OR SUPPLY issues (fewer drivers available, longer wait times causing cancellations). Must investigate both sides.
3. **Metric decomposition missing** — Should break down: Ride completions = Ride requests × Completion rate. Did requests drop? Or did requests stay the same but more rides got cancelled/timed out?
4. **No mention of app releases/deployments** — Should check if any code was deployed over the weekend that could have caused bugs.
5. **Structure could be tighter** — Good instincts but presented as a loose list rather than a clear framework (Verify → Segment → Decompose → Timeline → Hypothesize → Validate).

**Key lesson:** For marketplace products, always think about BOTH sides (supply + demand). Always decompose the metric into its components before hypothesizing. Always segment early — it's the fastest way to narrow down the problem.

### 2026-05-27 | Experimentation | Experiment design — missed key reason for A/B test and lacked specificity
**What was good:** Mentioned power/sample size thinking ("select count based on 5%"), guardrail metrics, p-value check. Good instinct to ask PM about expected effect size.
**What was missing/wrong:**
1. **Part 1 — Missed the MAIN statistical reason** why "ship and compare to last month" is bad: confounding variables. Many things change month-to-month (seasonality, new show releases, marketing campaigns, other feature launches). You can't attribute any change to the skip-recap feature because you have no control group running simultaneously. The risk of bugs is a secondary concern — the primary issue is you CAN'T ISOLATE THE EFFECT without a concurrent control.
2. **Part 2 — No specific metrics named** — What's the primary metric? "Watch time per session" is reasonable but should be stated explicitly. What are the guardrails? (e.g., episode completion rate shouldn't drop — maybe people skip recap and then feel lost and abandon the episode)
3. **No randomization unit stated** — User-level? Account-level? Device-level?
4. **No duration mentioned** — How long to run? Why?
5. **No hypothesis stated** — "Skipping recap saves time and reduces friction, leading users to watch more episodes per session" — stating the mechanism matters.
6. **"Select count of test customers based on 5%"** — This is vague. In an interview, you'd want to say: "Given a baseline of X, an MDE of 5% relative, 80% power, and alpha 0.05, I'd calculate the required sample size using a power calculation."

**Key lesson:** The #1 reason to A/B test (vs. ship-and-compare) is to ISOLATE the causal effect by having a simultaneous control group. Without it, you can't separate your feature's impact from everything else that changed. Always state: hypothesis, primary metric, randomization unit, duration, and guardrails explicitly.

### 2026-05-28 | Product Sense | Metric definition — improving structure but still thinking one-sided
**What improved:** ✅ Started with structure ("I'll structure this as a metrics question"). ✅ Clarified the goal first. ✅ Supporting metrics tell different stories (follows vs. comments). ✅ Guardrail mentioned.
**What was missing/wrong:**
1. **Only thinking about ONE side** — The feature has TWO user groups: (a) badge recipients (creators) and (b) content consumers (viewers). A strong answer measures success for BOTH. Does the badge motivate creators to post more/better content? AND does it help consumers find quality content?
2. **North Star is too narrow** — "Avg views of badged users' content" only measures the consumer side and only for badged users. A better North Star captures the full ecosystem effect: "Weekly content engagement rate across the platform" or "% of feed interactions on high-quality content."
3. **Goal could be sharper** — "Increase engagement" is generic. Sharper: "Incentivize high-quality content creation AND help consumers discover trustworthy expertise." This dual goal changes which metrics you pick.
4. **Guardrail is too generic** — "Weekly repeat users" is overall retention, not specific to this feature. Better guardrails: (a) Do non-badged creators feel discouraged and post LESS? (b) Does content diversity decrease (only badged users get visibility)? (c) Do users game the system with low-quality high-volume posts to get badges?
5. **Missing: creator-side metrics** — Post frequency of badged users (did the badge motivate them?), quality of posts (did it incentivize better content or just more content?), badge pursuit behavior (are non-badged users trying to earn it?).

**Key lesson:** For features that affect multiple user groups (creators + consumers, buyers + sellers), always measure success for EACH group separately. Ask: "Who does this feature serve, and how does each group benefit?"

### 2026-05-28 | Statistics | Alpha/power trade-off — correct direction but incomplete
**What was correct:** Correctly identified that stricter alpha + higher power requires more data (larger sample size).
**What was missing:** Only mentioned one trade-off (sample size). A complete interview answer includes the BUSINESS cost of needing more data:
1. **Longer experiment duration** — more sample = more days/weeks running the test. That's opportunity cost: you can't run other experiments on the same surface, and you delay shipping a potentially good feature.
2. **Opportunity cost** — while you're waiting for ultra-high confidence, competitors might ship faster. "Perfect is the enemy of good."
3. **Diminishing returns** — going from 80% power to 99% power might require 3x the sample size but only catches an extra 19% of true effects. Is that worth 3x the wait?
4. **The real-world framing** — "We choose 5%/80% because it balances the cost of being wrong (shipping a bad feature) against the cost of being slow (missing opportunities). Stricter thresholds make sense for high-stakes decisions (medical, irreversible) but are overkill for most product experiments."

**Key lesson:** When asked about trade-offs, always connect the statistical concept to the BUSINESS impact. "More data" → "more time" → "slower iteration" → "opportunity cost." Interviewers want to see you think beyond the math.

### 2026-05-29 | Product Sense | Conflicting metrics — strong investigation but missing the "so what" recommendation and ecosystem thinking
**What was good:** ✅ Verified data first. ✅ Segmented by platform. ✅ Formed a hypothesis (better recs → less browsing → fewer unique videos). ✅ Proposed a way to validate (check distribution of watch time per video). ✅ Checked temporal trends. This is the best-structured answer so far.
**What was missing:**
1. **No clear recommendation** — The question asked "ship, kill, or iterate?" and the answer didn't commit to a decision. In an interview, you MUST make a call and justify it. Even "I'd recommend iterating because..." is better than leaving it open.
2. **Missed the ecosystem/long-term concern** — The VP's worry isn't just about users watching fewer videos. It's about the CREATOR ecosystem. If the algorithm only recommends a few popular videos, small creators get no views → they stop creating → content supply shrinks → platform health degrades long-term. This is the "filter bubble" / "rich-get-richer" problem.
3. **Didn't address the satisfaction score** — The survey showed no change. This is important signal: users aren't happier OR unhappier. That suggests the watch time increase might be driven by the algorithm being "stickier" (autoplay-like behavior) rather than users genuinely enjoying content more.
4. **Missing: short-term vs. long-term framing** — Watch time up is good short-term. But less diversity could hurt long-term retention (users get bored of same content) and creator health. A strong answer explicitly names this tension.

**Key lesson:** For conflicting metrics questions, always: (1) Explain the mechanism causing the conflict, (2) Consider short-term vs. long-term implications, (3) Think about ecosystem effects (creators, not just consumers), (4) MAKE A RECOMMENDATION — don't leave it open.

### 2026-05-29 | Statistics/Probability | Bayes' Theorem — does not know how to apply
**Gap:** User does not know how to solve Bayes' theorem / conditional probability problems. This is a common interview question type (especially at Meta and Google) where you're given sensitivity, false positive rate, and base rate, and asked to calculate the probability of a condition given a positive test result.
**Concept to study:** Bayes' Theorem, base rate fallacy, prior probability, posterior probability. Practice with: medical test examples, fraud detection, spam filtering.
**Priority:** High — this comes up frequently in DS interviews and is testable at all FAANG companies.
