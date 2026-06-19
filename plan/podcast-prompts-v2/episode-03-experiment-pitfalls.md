# Episode 3: When Experiments Go Wrong — Pitfalls and Traps

## Instructions for Gemini

Create a conversational podcast episode (two hosts discussing) based on the detailed source material below. Make it engaging, story-driven, and slow-paced. The listener is a data professional learning experimentation concepts and learns best through examples and analogies.

Target: 20 minutes. Use ALL the material below — don't summarize, expand on it with conversation.

---

## SOURCE MATERIAL (use this as the basis for the episode):

### Pitfall 1: Peeking (Early Stopping)

**What it is:** Checking your A/B test results repeatedly before the planned end date and making a ship/kill decision when you see a "significant" result.

**Why it's dangerous:** Every time you check, you're running another statistical test. With alpha = 5%, each peek has a 5% chance of showing a false positive. Check 10 times → your real false positive rate balloons to ~40%, not 5%.

**Real-world story:** A PM at a startup checks the experiment dashboard every morning at 9am. On day 3, the dashboard shows p = 0.04 for the new checkout flow — "+15% conversion, significant!" They ship it. Two weeks later, they re-check: the effect has shrunk to +2% and is no longer significant. The day-3 result was a random fluctuation that happened to cross the significance threshold.

**Analogy:** It's like checking your stock portfolio every hour. At some point during the day, your portfolio will be "up" — but that doesn't mean you should sell. The more often you check, the more likely you'll see a random spike and act on noise.

**Mathematical intuition:** If you flip a fair coin 20 times, getting 12 heads isn't that surprising (p ≈ 0.25). But if you flip the coin 20 times, and ALSO check after 5 flips, 10 flips, and 15 flips — the chance you'll see a "streak" at any checkpoint is much higher. Each checkpoint is an opportunity for random noise to fool you.

**How to prevent it:**
1. Calculate sample size BEFORE the experiment. Commit to the end date.
2. Use sequential testing methods (like always-valid p-values or group sequential design) that account for multiple looks.
3. Only look at guardrail metrics during the experiment (for safety), not the primary metric.
4. If you must peek, use a Bonferroni correction: if you plan to look 5 times, use alpha = 0.05/5 = 0.01 per peek.

**Interview line:** "I'd commit to the sample size and end date upfront. If we need to peek for business reasons, I'd use sequential testing methods that control the overall false positive rate across multiple looks."

---

### Pitfall 2: Novelty Effect

**What it is:** Users engage more with a new feature simply because it's NEW and different, not because it's genuinely better. The inflated engagement fades as the novelty wears off.

**Real-world story:** Facebook adds a new "reaction" emoji (Hug). In week 1, reactions usage jumps 40%. Everyone is trying the new Hug emoji. PMs celebrate. By week 4, the Hug emoji usage is only +5% above the old baseline. People were just experimenting. The true long-term impact was +5%, not +40%.

**Another story:** Snapchat redesigns its Discover page. Usage spikes because everyone is exploring the new layout. After 3 weeks, engagement is back to where it started. The redesign didn't add value — it just temporarily disrupted habits.

**How to detect it:**
- Compare week 1 effect vs. week 3-4 effect. If it decays, novelty was inflating it.
- Look at "experienced users" separately — users who've had 7+ days of exposure. Their steady-state behavior is the truth.
- The pattern looks like: spike → decay → plateau. The plateau is the real effect.

**How to prevent it:**
- Run experiments for minimum 2-3 weeks (not 1 week).
- Report the "steady-state" effect, not the peak effect.
- In your recommendation, note: "The full effect is +X%, but the stabilized effect after novelty decay is +Y%."

**Interview line:** "I'd run for at least 2 weeks and compare week 1 vs. week 2+ to account for novelty decay. The real effect is the plateau, not the initial spike."

---

### Pitfall 3: Primacy Effect (the opposite of novelty)

**What it is:** Users engage LESS with a change initially because they're used to the old way. Performance looks bad early, but improves as users adapt. If you kill the experiment too early, you destroy a good feature.

**Real-world story:** YouTube changes the homepage from a grid layout to a feed layout. Week 1: clicks drop 8%. The design team panics. Week 2: clicks are -4%. Week 3: clicks are -1%. Week 4: clicks are +3%. Users needed time to learn the new layout. If they'd killed it after week 1, they would have lost a +3% improvement.

**Another story:** Gmail redesigns the compose window. Initial user satisfaction drops. Users complain on Twitter. But usage data shows that after 2 weeks, people compose emails faster. The new design was objectively better — people just hated change initially.

**How to detect it:**
- The pattern is: dip → recovery → plateau (or improvement). Opposite of novelty.
- If the metric is getting BETTER over time (not worse), it's likely primacy.
- Segment by "how long has this user been exposed?" — long-exposure users should show the true effect.

**Interview line:** "I'd check if the negative effect is improving week-over-week. If it is, that's likely a primacy/adjustment effect, and I'd recommend extending the experiment before making a kill decision."

---

### Pitfall 4: Simpson's Paradox

**What it is:** A trend that appears in overall/aggregated data REVERSES when you break it down by segments. The overall number tells a different story than the segment-level numbers.

**Real-world story — the UC Berkeley admission case:** UC Berkeley was accused of gender bias. Overall, 44% of men were admitted vs. 35% of women. Looks discriminatory. But when you look department by department, women had EQUAL or HIGHER admission rates in most departments. What happened? Women applied more to highly competitive departments with low acceptance rates. Men applied more to less competitive departments. The MIX of where they applied — not bias — drove the overall difference.

**Product example:** An e-commerce site runs an A/B test on a new checkout flow.
- Overall: New flow has 5% higher conversion. Ship it!
- Segment by device: Mobile conversion went DOWN 2%. Desktop conversion went DOWN 1%.
- What happened? During the test period, traffic mix shifted heavily toward desktop (which has higher baseline conversion). The mix shift — not the new flow — drove the overall improvement. The new flow actually HURT conversion on both platforms.

**Another product example:** "Average revenue per user went up this month!" But when you segment: revenue went down for new users AND returning users. What happened? The proportion of returning users (who spend more) increased. Nobody is spending more — the customer mix just shifted toward higher-spenders.

**How to detect it:**
- ALWAYS segment your results by key dimensions (platform, user type, geography, traffic source).
- If the overall trend doesn't hold within segments, you have Simpson's Paradox.
- Check if the SIZE of segments changed between groups or time periods.

**How to prevent being fooled:**
- In A/B tests: check that segment proportions are balanced between treatment and control.
- In time comparisons: check if the mix of users changed over time.
- Rule: "If an overall metric moves, but no individual segment moved in that direction, look for a mix shift."

**Interview line:** "I'd segment by key dimensions to check for Simpson's Paradox. If the overall improvement isn't consistent across segments, it might be driven by a mix shift rather than a genuine improvement."

---

### Pitfall 5: Twyman's Law

**What it is:** "Any figure that looks interesting or different is usually wrong." Named after Tony Twyman, a researcher who noticed that surprisingly extreme results almost always turned out to be data errors.

**Real-world story:** A DS at Microsoft runs an experiment. The result shows +50% improvement in click-through rate. Everyone is excited. The DS investigates and discovers a logging bug — the treatment group had double-counted clicks due to a JavaScript error. The actual effect was +2%.

**Another story:** "Revenue doubled in Brazil this week!" Investigation reveals the currency conversion table was updated incorrectly — BRL was being converted at 10x the correct USD rate.

**The rule:** The MORE surprising a result looks, the MORE likely it's a data quality issue. Before investigating WHY a metric moved, always verify THAT the metric actually moved correctly.

**Common causes of "interesting" but wrong figures:**
- Logging/tracking bugs (double-counting, missing events)
- Data pipeline failures (missing rows, delayed data)
- Definition changes (someone changed how the metric is calculated)
- Bot/spam traffic spikes
- Currency/timezone/unit errors

**Interview line:** "My first instinct with any surprising number is Twyman's Law — I'd verify the data is correct before investigating the product. In my experience, the most extreme-looking changes are usually instrumentation issues."

---

### Pitfall 6: SUTVA Violation (Network Effects / Interference)

**What it is:** SUTVA = Stable Unit Treatment Value Assumption. It assumes that one user's treatment doesn't affect another user's outcome. When this is violated, your A/B test results are biased because control users are contaminated by treatment users.

**Real-world story:** Facebook tests a new "Share" button redesign. User A (treatment) shares a post using the new button. User B (control) sees the shared post in their feed. User B's engagement is now affected by User A's treatment — even though B is in the control group. The control group's metrics are contaminated.

**Uber marketplace example:** Uber tests a new surge pricing algorithm for riders. Treatment riders get the new pricing, control riders get the old pricing. But there's a problem: if treatment riders cancel more (due to higher prices), those drivers become available for control riders. Control riders now get shorter wait times. The treatment HELPED the control group by freeing up supply. The measured effect is biased downward.

**Instagram example:** Instagram tests "Close Friends Story Reactions." User A (treatment) has the feature — only close friends can react to their stories. User B (control) follows User A. User B's experience is directly changed by User A's treatment. They can no longer react to User A's stories normally.

**When SUTVA is violated:**
- Social features (messaging, sharing, reactions)
- Marketplace products (drivers/riders, buyers/sellers — supply is shared)
- Network products (any feature where users interact)
- Pricing experiments (one group's pricing affects the other group's availability)

**How to fix it:**
1. **Cluster randomization:** Randomize groups of connected users together (entire friend groups, geographic clusters)
2. **Geo-level randomization:** Assign entire cities/regions to treatment or control
3. **Switchback experiments:** Alternate treatment/control across time windows (e.g., surge pricing ON for all users Mon/Wed/Fri, OFF Tue/Thu)
4. **Network-based splitting:** Use graph algorithms to find communities with few cross-connections

**Trade-off:** Cluster randomization needs MORE clusters (more cities, more friend groups) to get statistical power. You lose the per-user precision of individual randomization.

**Interview line:** "I'd be concerned about SUTVA violations here because users in treatment and control interact. I'd recommend cluster-level randomization — assigning entire friend groups or geographic regions to treatment or control to minimize cross-contamination."

---

### How to Tie It All Together in an Interview

If an interviewer asks: "What could go wrong with this experiment?" — hit 2-3 of these:

1. "I'd watch for **novelty/primacy effects** — running for 2+ weeks to see the stable effect."
2. "I'd check for **SUTVA violations** if users interact with each other."
3. "I'd establish a **peeking protocol** — sequential testing if we need to look early."
4. "I'd segment results to check for **Simpson's Paradox** — making sure the effect is consistent."
5. "And per Twyman's Law, if results look too good, I'd **verify the data** before celebrating."

---

## PODCAST STYLE INSTRUCTIONS:

- Two hosts discussing: one explains, one asks clarifying questions and "what about..." follow-ups
- Use ALL six pitfalls with ALL the examples above
- For each pitfall: tell the story first, then explain the mechanism, then give the prevention strategy
- Keep it conversational — "So wait, you're telling me that checking your results too often actually INCREASES false positives?" "Exactly..."
- Pace: slow, repeat key ideas, pause between pitfalls
- End with: "If you remember nothing else: any time a result surprises you, check the data first. And always segment."
