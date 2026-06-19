# Episode 1: A/B Testing Fundamentals — The Mental Model

## Instructions for Gemini

Create a conversational podcast episode (two hosts discussing) based on the detailed source material below. Make it engaging, story-driven, and slow-paced. The listener is a data professional who works with data daily (SQL, dashboards) but hasn't designed experiments from scratch. They learn best through examples and analogies — not abstract definitions.

Target: 20 minutes. Use ALL the material below — don't summarize, expand on it with conversation.

---

## SOURCE MATERIAL (use this as the basis for the episode):

### What is an A/B Test? (The Core Concept)

**One-sentence definition:** An A/B test is a controlled experiment where you show two groups of users different experiences simultaneously, and compare their behavior to determine which experience is better.

**The simplest analogy:** A taste test at a grocery store. You give half the people the old recipe cookies and half the new recipe cookies. Same people, same day, same conditions — only difference is the cookie. Whichever group says "yum" more tells you which recipe is better.

**Why "simultaneously" matters:** You can't compare this month's sales to last month's sales and call it a test. Too many things change between months: weather, holidays, competitor actions, marketing spend, even your own other product changes. A simultaneous comparison eliminates all that noise because BOTH groups experience the same external conditions.

**Real-world scale:** Amazon runs thousands of A/B tests simultaneously. Netflix tests everything from thumbnail images to recommendation algorithms. Google famously tested 41 shades of blue for link colors. At this scale, even a 0.1% improvement translates to millions in revenue.

---

### The Two Groups: Control and Treatment

**Control group:** Sees the existing experience. Nothing changes for them. They're your baseline — "what would have happened anyway."

**Treatment group:** Sees the new experience. This is the change you want to evaluate.

**Example — Amazon "Add to Cart" button:**
- Control: 500,000 users see the current orange "Add to Cart" button
- Treatment: 500,000 users see a new green "Add to Cart" button
- Both groups use Amazon at the same time, on the same products, during the same week
- After 2 weeks, you compare: did the green button group add more items to their cart?

**Example — Netflix thumbnail:**
- Control: Users see the original thumbnail for "Stranger Things" (a dark, moody image)
- Treatment: Users see a new thumbnail (the kids on bikes, more adventurous)
- Same show, same users, same time period
- Measure: click-through rate on the thumbnail

**Example — Spotify Discover Weekly algorithm:**
- Control: Users get recommendations from the current algorithm
- Treatment: Users get recommendations from the new algorithm
- Measure: songs listened past 30 seconds, skip rate, saves to playlist

---

### Why Randomization Matters

**The principle:** Users must be assigned to control or treatment RANDOMLY. You can't let users choose, and you can't hand-pick who goes where.

**Why? Selection bias.**

**Restaurant analogy:** A restaurant wants to test a new dish. They serve the new dish to regulars (who love the restaurant and come often) and the old dish to first-time visitors (who are still deciding if they like the place). The regulars rate the new dish highly. Did the dish cause the high rating, or were regulars going to rate anything highly? You can't tell. The groups were different BEFORE the test started.

**Product example of what goes wrong without randomization:** A PM wants to test a new onboarding flow. Instead of randomizing, they give the new flow to users who sign up from paid ads, and keep the old flow for organic sign-ups. Result: the new flow shows worse retention. But is that because the flow is bad, or because paid users are naturally less committed? You'll never know. The groups weren't comparable.

**What good randomization gives you:** When you randomly split 1 million users into two groups of 500,000, those groups will be nearly identical on EVERY dimension: age, geography, device, past behavior, engagement level, spending habits. The only difference between them is the experience you're testing. So any difference in outcome MUST be caused by the experience.

**How companies do it in practice:** Most experimentation platforms (like Amazon's Weblab) hash the user ID to determine their group. Hash(user_id) mod 100 < 50 → control, ≥ 50 → treatment. This is deterministic (same user always in same group) and balanced.

---

### Statistical Significance — What It Actually Means

**The core question:** "Is the difference I'm seeing REAL, or could it just be random luck?"

**Coin flip analogy (build up slowly):**
- You flip a coin 10 times, get 7 heads. Is the coin unfair? Probably not — 7/10 isn't that weird with a fair coin. You'd see that roughly 17% of the time with a fair coin.
- You flip a coin 100 times, get 70 heads. Getting more suspicious... but still possible (about 0.004% chance with a fair coin).
- You flip a coin 10,000 times, get 7,000 heads. The coin is DEFINITELY unfair. This basically never happens by chance with a fair coin.
- The SAME ratio (70%) tells you very different things depending on how much data you have. More data = more confidence that the pattern is real, not luck.

**In A/B test terms:** Treatment shows 4.5% conversion vs. control's 4.2%.
- With 100 users per group: that 0.3% difference is probably noise. Sample too small.
- With 100,000 users per group: that 0.3% difference is almost certainly real. Too many data points for it to be a fluke.

**Statistical significance = "I'm confident enough that this isn't just random noise."**

---

### P-Values — Demystified

**What a p-value IS:**
"The probability of seeing a result THIS extreme (or more extreme) IF there was actually NO real difference between the groups."

**Translation:** "If the green button was actually no better than the orange button, what are the chances I'd still see a 0.3% gap just by random luck? If those chances are very low (say 2%), then I'm confident the gap is real."

**Example with numbers:**
- Your experiment shows: treatment 4.5% vs. control 4.2%, p = 0.03
- Translation: "If the green button truly had NO effect, there's only a 3% chance I'd see a gap this large just from random variation in who ended up in each group."
- Since 3% is below our threshold of 5%, we call it "statistically significant" — we believe the effect is real.

**What a p-value is NOT:**
- ❌ NOT "the probability that the treatment works" (common misconception)
- ❌ NOT "the probability the result is wrong"
- ✅ It IS "the probability of the DATA given that the treatment has NO effect"

**The 5% threshold (alpha):**
- Industry convention: if p < 0.05, we call it significant
- This means we accept a 5% chance of declaring a result "real" when it's actually noise (Type I error / false positive)
- Why 5%? It's a balance between being too cautious (missing real effects) and too loose (shipping noise). Not magic — just convention.

---

### Statistical Significance vs. Practical Significance

**The crucial distinction that separates good data scientists from average ones.**

**Statistical significance asks:** "Is the effect real?" (yes/no, based on sample size and p-value)

**Practical significance asks:** "Is the effect big enough to matter?" (a business judgment)

**Example where they diverge:**
- You have 10 million users in your experiment. The green button shows +0.01% conversion vs. orange button. P-value = 0.001 (highly statistically significant!).
- But 0.01% improvement on a 4% baseline means roughly 1 extra purchase per 10,000 users. At scale, that might be 100 extra purchases per day.
- Is it worth the engineering effort to change the button? The cost of maintaining the new button code? The risk of unintended side effects?
- Maybe. Maybe not. That's a business decision, not a statistics decision.

**Another example:**
- You test a new recommendation algorithm. It shows +5% increase in click-through rate, p = 0.04.
- Statistically significant AND practically significant — a 5% CTR improvement on a recommendation engine could mean millions in ad revenue.
- Easy ship decision.

**The matrix:**

| | Statistically Significant | Not Statistically Significant |
|---|---|---|
| **Practically Large** | Ship it ✅ | Probably underpowered — run longer |
| **Practically Small** | Probably not worth it | Don't ship |

**Interview line:** "I'd look at both statistical significance and practical significance. A result can be statistically significant but too small to justify the engineering investment. I'd translate the effect size into business impact — how many dollars, users, or actions does this represent?"

---

### Why You Can't Just "Look at the Numbers"

**The wrong approach (before-after comparison):**
"We launched the feature on Monday. Last week's metric was 4.2%. This week's metric is 4.5%. The feature caused a 0.3% improvement!"

**Why this is unreliable — the confounders:**
1. **Seasonality:** Maybe this week always has higher conversion (payday, weekend, holiday)
2. **Other changes:** Another team launched a different feature the same day
3. **Marketing:** A new ad campaign started driving different traffic
4. **Trend:** The metric was already trending upward for months
5. **External events:** A competitor had an outage, sending users to you

**A real story:** A team at a company launched a "speed improvement" on Tuesday. Wednesday: metrics up 10%. They celebrated. Thursday: someone pointed out that the previous Tuesday had been the Super Bowl (US users watching football instead of shopping). The "improvement" was just normal traffic resuming after an unusual day.

**Why A/B testing solves this:** Both groups experience the Super Bowl. Both groups experience the new ad campaign. Both groups experience seasonality. The only thing different between them is YOUR change. Any difference MUST be from your change, because everything else is identical across groups.

---

### Putting It All Together — How a Real A/B Test Works End-to-End

**Scenario:** You're a DS at DoorDash. The PM wants to test showing "Estimated delivery time: 25 mins" more prominently on the restaurant listing page.

**Step 1: Hypothesis**
"Showing delivery time prominently will help users choose restaurants faster, increasing order completion."

**Step 2: Metrics**
- Primary (OEC): Order completion rate (% of sessions → completed order)
- Secondary: Time from app open to order placed
- Guardrails: Average order value (shouldn't drop), customer satisfaction

**Step 3: Randomization**
Randomly assign users 50/50. Use user-level randomization (each user always in the same group).

**Step 4: Sample size**
Baseline completion rate: 35%. Want to detect 2% relative improvement (35% → 35.7%). At 80% power, need ~200,000 users per group. DoorDash has 2M daily users → need 1 day at 50/50 split. But run for 2 weeks (weekday/weekend effects + novelty buffer).

**Step 5: Run**
Monitor guardrails daily. Don't peek at primary metric.

**Step 6: Analyze (after 2 weeks)**
Compare completion rate: treatment 36.1% vs. control 35.2%. Difference = 0.9pp. p = 0.008. Statistically significant.

**Step 7: Decision**
Effect is real (+2.6% relative), guardrails clean, effect stable week-over-week. Recommend ship.

---

## PODCAST STYLE INSTRUCTIONS:

- Two hosts discussing: one explains (the "teacher"), one asks questions and says "wait, so let me make sure I understand..." (the "learner")
- Start with "What IS an A/B test?" at the most basic level, then build up concept by concept
- Use ALL the examples above — Amazon button, Netflix thumbnail, Spotify algorithm, DoorDash delivery time
- For each concept: give the analogy first, then the product example, then the precise definition
- The learner host should ask the "dumb questions" that listeners are thinking: "But why can't we just compare this week to last week?" "What does p = 0.03 actually mean in English?"
- Pace: SLOW. Repeat key ideas in different words. Pause between major concepts.
- End with the DoorDash end-to-end example as a capstone that ties everything together
- Final takeaway: "An A/B test is just a fair, simultaneous comparison where the only difference between groups is the thing you're testing. Randomization makes the groups comparable. Statistical significance tells you if the result is real or luck. Practical significance tells you if it's worth shipping."
