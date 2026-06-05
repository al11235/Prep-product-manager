# Experimentation & A/B Testing Questions

Your "Trustworthy Online Controlled Experiments" book is the best resource for this category.
This is a differentiator — most PM candidates have surface-level A/B testing knowledge.

---

## Experiment Design
1. Walk me through how you'd design an A/B test for a new checkout flow.
2. How do you determine sample size and experiment duration?
3. You want to test a new pricing model. Can you A/B test this? What are the challenges?
4. How would you design an experiment for a feature with network effects (e.g., messaging)?
5. You're testing a new recommendation algorithm. What's your control? What do you measure?

## Statistical Foundations
6. Explain statistical significance in plain language. What does p < 0.05 actually mean?
7. What's the difference between statistical significance and practical significance?
8. What is statistical power and why does it matter for experiment design?
9. Explain Type I and Type II errors with a product example.
10. What's multiple testing correction and when do you need it?

## Metrics & OEC
11. How do you choose an Overall Evaluation Criterion (OEC) for an experiment?
12. Your experiment improves click-through rate but hurts long-term retention. What do you do?
13. How do you balance short-term metrics vs. long-term metrics in experiment evaluation?
14. What are guardrail metrics and why are they important?
15. How would you construct a composite metric (OEC) for a search engine?

## Common Pitfalls
16. What is novelty effect and how do you account for it?
17. Explain Simpson's paradox with a product example.
18. What are carryover effects and how do they impact experiments?
19. How do you detect if randomization failed in your experiment?
20. What is peeking (early stopping) and why is it dangerous?

## Advanced / Edge Cases
21. You can't randomize at the user level. What alternatives exist? (cluster randomization, geo experiments)
22. How do you handle experiments where the treatment effect takes weeks to materialize?
23. Your experiment shows a statistically significant 0.1% improvement. Ship or not?
24. How do you run experiments on features that affect supply and demand simultaneously (marketplace)?
25. What's an interleaving experiment and when would you use it over A/B testing?

## Decision-Making
26. Your A/B test is inconclusive after 4 weeks. What do you do?
27. The experiment shows positive results but engineering cost to productionize is high. How do you decide?
28. Two teams want to run conflicting experiments on the same surface. How do you resolve this?
29. Leadership wants to ship a feature without testing. How do you push back?
30. How do you build an experimentation culture in an organization that doesn't have one?

---

## Key Concepts from "Trustworthy Online Controlled Experiments"

### Must-Know for Interviews
| Concept | One-liner | Interview Use |
|---------|-----------|---------------|
| OEC | Single metric that captures experiment success | "How would you measure this?" |
| Guardrail metrics | Metrics you don't want to degrade | Show trade-off awareness |
| Statistical power | Probability of detecting a real effect | "How long to run?" |
| Novelty/primacy effects | Users react differently to new things | "What could go wrong?" |
| Intention-to-treat | Analyze based on assignment, not usage | Show rigor |
| Instrumentation | Logging and tracking setup | "How would you implement?" |
| Twyman's Law | "Any figure that looks interesting is usually wrong" | Show healthy skepticism |
| Experiment velocity | Ship more experiments = learn faster | Strategy discussions |

### Book Chapters → Interview Mapping
- Ch 2 (Running experiments) → End-to-end design questions
- Ch 3 (Twyman's Law) → Data quality and skepticism
- Ch 5 (Speed matters) → Latency experiments, product sense
- Ch 7 (Metrics) → OEC and metric selection
- Ch 11 (Observational studies) → When you can't A/B test
- Ch 17 (Pitfalls) → "What could go wrong?" follow-ups
- Ch 19 (Organizational) → Culture and process questions

---

## Your Edge as a BIE
- You've likely run or supported Weblab experiments at Amazon
- You understand data pipelines that feed experiment analysis
- You can speak to instrumentation challenges from experience
- You know the difference between "the data says X" and "we can trust the data says X"
- Frame this as: "I've seen experiments fail because of bad instrumentation / wrong metrics / insufficient power — here's what I learned"
