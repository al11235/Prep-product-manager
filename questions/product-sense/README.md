# Product Sense & Metrics Questions (Product DS Angle)

For Product DS, product sense is about MEASURING and DIAGNOSING, not designing features.
You're the person who defines what success looks like and proves whether something worked.

---

## Metric Definition & Selection

1. You're the DS for Instagram Reels. Define the North Star metric and 3 supporting metrics.
2. How would you measure success for a new onboarding flow?
3. Define an OEC (Overall Evaluation Criterion) for YouTube's recommendation algorithm.
4. What metrics would you track for a food delivery app? Organize them into a metric tree.
5. You're DS for Alexa. How do you measure "user satisfaction" for a voice assistant?
6. Define success metrics for a subscription service. How do leading vs. lagging indicators differ here?
7. How would you measure the health of a two-sided marketplace (e.g., Uber)?
8. What's the difference between a vanity metric and an actionable metric? Give examples.

## Metric Diagnosis (Root Cause Analysis)

9. DAU dropped 10% week-over-week. Walk me through your investigation.
10. Conversion rate is up 5% but revenue is flat. What's happening?
11. Average session duration increased 20%. Is this good or bad? How do you determine?
12. Notification open rates dropped 30% after an app update. Diagnose.
13. A/B test shows engagement up but user satisfaction (NPS) down. What do you recommend?
14. Revenue per user increased but total revenue decreased. Explain possible causes.
15. Your search ranking metric improved but customer complaints increased. What's going on?
16. Retention improved for new users but declined for power users. What do you investigate?

## Trade-offs & Recommendations

17. Should you optimize for short-term engagement or long-term retention? How do you decide?
18. Your experiment shows a 0.5% improvement in conversion. Engineering cost to productionize is high. Ship or not?
19. Two features compete for the same surface area. How do you use data to decide which wins?
20. A feature helps 80% of users but hurts 20%. How do you think about this?
21. Personalization improves engagement but creates filter bubbles. How do you balance?
22. Your model improves relevance but increases latency by 200ms. What's your recommendation?

## Product Sense (DS-flavored design)

23. How would you use data to decide what to build next for Amazon Prime?
24. A PM proposes a new feature. What questions do you ask before agreeing to measure it?
25. How would you design a metric framework for a brand-new product with no historical data?
26. You're DS for a social app. How do you measure "meaningful social interactions" vs. passive scrolling?
27. How would you quantify the value of reducing app load time by 1 second?
28. A PM says "users love this feature" based on qualitative feedback. How do you validate quantitatively?

---

## Framework: Metric Diagnosis

When asked "X metric changed, diagnose it":

1. **Clarify** — Which metric exactly? What time period? How is it measured?
2. **Segment** — Break down by platform, geography, user cohort, new vs. returning
3. **Timeline** — When did it start? Gradual or sudden? Correlate with releases/events
4. **Hypothesize** — List 3–4 possible causes ranked by likelihood
5. **Validate** — What data would confirm/reject each hypothesis?
6. **Recommend** — Based on findings, what action do you suggest?

---

## Tips
- Always ask "compared to what?" — absolute numbers mean nothing without context
- Show you think about metric GAMING — how could this metric be gamed or misleading?
- Mention segments naturally: "I'd first check if this is driven by a specific cohort"
- Connect metrics to user value, not just business value
- Reference your experimentation book: OEC thinking, guardrail metrics
