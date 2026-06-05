# Metric Diagnosis Framework

Use this when asked: "Metric X changed. What happened?" or "Investigate why Y dropped."

---

## The Framework (6 Steps)

### 1. CLARIFY the metric
- What exactly is the metric? How is it calculated?
- What's the magnitude of change? (10% drop vs. 0.5% drop = very different urgency)
- What time period? Sudden or gradual?
- Is this a rate, count, or ratio? (each has different failure modes)

### 2. CHECK data quality first
- Is the logging/instrumentation working correctly?
- Any recent deployments that could affect tracking?
- Twyman's Law: "Any figure that looks interesting is usually wrong" — verify before investigating

### 3. SEGMENT the data
Break down by:
- **Platform**: iOS vs. Android vs. Web
- **Geography**: country, region
- **User type**: new vs. returning, free vs. paid
- **Cohort**: signup date, tenure
- **Source**: organic vs. paid, channel
- **Device**: mobile vs. desktop

Ask: "Is this broad-based or concentrated in one segment?"

### 4. CORRELATE with timeline
- When exactly did the change start?
- What happened around that time?
  - Product releases / deployments
  - Marketing campaigns started/stopped
  - Seasonality / holidays
  - Competitor actions
  - External events (outages, news)
  - Algorithm/model updates

### 5. HYPOTHESIZE (rank by likelihood)
List 3–5 hypotheses. For each:
- What's the mechanism? (how would this cause the observed change?)
- What data would confirm or reject it?
- How likely is it given what we know?

### 6. RECOMMEND action
- If confirmed: what's the fix? What's the urgency?
- If inconclusive: what additional data/analysis do you need?
- What's the business impact of NOT acting?

---

## Example

> "Push notification open rates dropped 30% this week."

**Clarify**: Open rate = opens / sends. 30% relative drop (e.g., 20% → 14%). Started Monday.

**Data quality**: Check if notification delivery logging changed. Any SDK updates?

**Segment**:
- By platform: iOS dropped 45%, Android flat → likely iOS-specific
- By notification type: promotional dropped, transactional unchanged

**Timeline**: iOS 18.2 update rolled out last weekend → timing matches

**Hypotheses**:
1. iOS update changed notification permissions/display (most likely)
2. Content quality degraded (less likely — transactional unaffected)
3. Send time optimization broke (check — timing unchanged)

**Recommend**: Investigate iOS notification permission changes in new OS version. Check if users need to re-grant permissions. Short-term: adjust for iOS display changes. Long-term: diversify engagement channels.

---

## Common Pitfalls
- ❌ Jumping to conclusions without checking data quality
- ❌ Looking at only one segment
- ❌ Confusing correlation with causation
- ❌ Not quantifying the business impact
- ❌ Forgetting to check if the metric DEFINITION changed (denominator shift)
- ❌ Ignoring Simpson's paradox (overall trend hides segment-level truth)
