# Making Prep Fun — Novel & Creative Methods

Studying for months is a grind. Here's how to keep it engaging so you actually stick with it.

---

## 🎮 1. Gamification — Turn Prep into a Game

### The XP System
Track your progress like an RPG character. Earn XP for activities:

| Activity | XP |
|----------|-----|
| Complete a timed practice question | +10 |
| Mock interview with Kiro | +25 |
| Finish a book chapter | +15 |
| LeetCode SQL problem (medium) | +10 |
| LeetCode SQL problem (hard) | +20 |
| Write up a STAR story | +15 |
| Product teardown (see below) | +30 |
| Streak bonus (7 days in a row) | +50 |

**Levels:**
- 0–100 XP: Novice Analyst
- 100–300 XP: Data Explorer
- 300–600 XP: Metric Detective
- 600–1000 XP: Experiment Architect
- 1000–1500 XP: Product DS Candidate
- 1500+ XP: Interview Ready 🎯

### Daily Streak Challenge
Like Duolingo — don't break the chain. Even 15 minutes counts. Track in a simple calendar.

---

## 🔬 2. Product Teardowns — Learn by Reverse-Engineering Real Products

Pick a product you USE daily and analyze it like a DS would. This builds product sense naturally.

### Weekly Teardown Template (30–45 min)

**Pick one product** (Instagram, Uber, Spotify, Amazon, etc.) and answer:

1. **What's the North Star metric?** Why?
2. **Draw the metric tree** — how does the North Star decompose?
3. **What experiment would you run?** Pick one feature and design an A/B test.
4. **Something feels off** — invent a scenario: "What if [metric] dropped 20%?" Walk through diagnosis.
5. **What would YOU build next?** Use data reasoning to justify.

### Why This Works
- You're practicing product sense on products you already understand
- It's more engaging than abstract questions
- You build a portfolio of examples to reference in interviews
- Save teardowns in `case-studies/` — they become your answer bank

---

## 🎲 3. Probability Through Games & Simulations

Instead of memorizing formulas, BUILD intuition through play.

### Games That Teach Probability
- **Poker** — conditional probability, Bayesian updating, expected value
- **Settlers of Catan** — probability distributions (dice rolls), risk assessment
- **Blackjack** — conditional probability, decision under uncertainty
- **Wordle** — information theory, Bayesian elimination

### Simulation Challenges (Python)
Write quick simulations to verify your intuition:
- Simulate the Monty Hall problem (1000 trials)
- Simulate A/B test false positive rates with peeking
- Simulate how sample size affects confidence interval width
- Simulate the birthday paradox
- Simulate coin flip streaks — how long until 10 heads in a row?

These are fun to code AND directly relevant to experimentation interviews.

### Interactive Tools
- [Seeing Theory](https://seeing-theory.brown.edu/) — Beautiful visual probability
- [StatSim](https://statsim.com/) — Free probabilistic simulation web app
- [Evan Miller's tools](https://www.evanmiller.org/ab-testing/) — A/B test calculators to play with

---

## 🗣️ 4. "Explain Like I'm 5" Challenge

Pick a concept and explain it in the simplest possible terms. Record yourself (voice memo) or type it out.

### Why This Works
- Interviewers LOVE candidates who explain clearly
- Forces you to truly understand, not just memorize
- Directly practices the communication skill tested in every round

### Weekly ELI5 Challenges
- Week 1: Explain p-values to your non-tech friend
- Week 2: Explain A/B testing to your grandmother
- Week 3: Explain confidence intervals using a cooking analogy
- Week 4: Explain Simpson's paradox using a sports example
- Week 5: Explain causal inference vs. correlation to a PM
- Week 6: Explain statistical power using a metal detector analogy

---

## 📰 5. "Data Scientist in the Wild" — Daily News Analysis

Spend 10 minutes reading tech news and think like a DS:

### The Exercise
1. Read one article about a product launch, feature change, or company metric
2. Ask yourself:
   - "How would I measure if this was successful?"
   - "What experiment would I run?"
   - "What could go wrong with this metric?"

### Sources
- TechCrunch, The Verge (product launches)
- Company earnings calls (metric discussions)
- Stratechery (strategy + data thinking)
- Company engineering blogs (experiment write-ups)

### Why This Works
- Builds product sense passively, without "studying"
- Gives you fresh examples for interviews ("I was reading about X and thought...")
- Keeps you current on industry trends

---

## 🃏 6. Spaced Repetition Flashcards (Anki)

There's a pre-made [Data Science Interview Anki deck](https://ankiweb.net/shared/info/1443276573) covering statistics and ML theory.

### Build Your Own Cards For:
- Statistical concept → product application (not just definition)
- "When would you use [test/method]?" → answer with example
- Key numbers to remember (z-scores, common distributions, power formulas)
- Experimentation pitfalls from your book

### Rules for Good Cards
- One concept per card
- Use questions, not statements ("When would you use a chi-squared test?" not "Chi-squared test is...")
- Include a real-world example on the answer side
- Review 5–10 cards daily (5 minutes)

---

## 🎭 7. Role-Play Scenarios with Kiro

Instead of just answering questions, simulate real work scenarios:

### "You're the DS on this team" Scenarios
- "You just joined the Instagram Reels team. It's your first week. The PM asks you to define success metrics for a new creator tool. Go."
- "You're in a meeting. The VP asks why DAU dropped. You have 2 minutes to give a structured answer with what you'd investigate."
- "An engineer proposes a feature. The PM loves it. You think the data doesn't support it. Role-play the conversation."

### "Teach Me" Mode
- Ask Kiro to play a confused PM and YOU explain statistical concepts
- This practices the cross-functional communication tested at Meta

---

## 🏃 8. Speed Rounds — Build Interview Stamina

### 5-Minute Drills
Set a timer. Answer as fast as you can:
- "Name 5 metrics for [product]" — GO
- "3 reasons a metric could drop" — GO
- "Design an A/B test in 5 sentences" — GO

### Why This Works
- Real interviews are time-pressured
- Builds confidence in thinking on your feet
- Reveals which concepts you ACTUALLY know vs. think you know

---

## 🧩 9. The "Metric of the Day" Ritual

Every morning, pick ONE metric from a product you use and think about it for 5 minutes:

- How is it probably calculated?
- What could make it go up or down?
- What's the guardrail metric?
- How would you A/B test an improvement?

Products to rotate: Amazon, Instagram, Uber, Spotify, Netflix, YouTube, Slack, LinkedIn

---

## 📊 10. Build a Mini-Project (Weekend Deep Dive)

Once a month, do a small data project that's interview-relevant:

### Project Ideas
1. **Analyze a public A/B test dataset** — find one on Kaggle, run full analysis
2. **Build a retention analysis** — use any app usage dataset
3. **Simulate an experimentation platform** — Python script that runs fake A/B tests with various pitfalls
4. **Metric dashboard** — pick a public company, estimate their key metrics from earnings data
5. **Causal inference exercise** — find an observational dataset, apply diff-in-diff

### Why This Works
- Gives you REAL examples to talk about in interviews
- More engaging than abstract practice
- Builds Python skills naturally
- "I recently did a project where I..." is powerful in behavioral rounds

---

## Combining Methods — Sample Fun Week

| Day | Activity | Method | Time |
|-----|----------|--------|------|
| Mon | Product teardown: Spotify | 🔬 Teardown | 30 min |
| Tue | 3 SQL problems + speed round | 🏃 Speed + LeetCode | 40 min |
| Wed | Simulate A/B test peeking in Python | 🎲 Simulation | 45 min |
| Thu | Mock interview with Kiro | 🎭 Role-play | 40 min |
| Fri | ELI5: Explain CUPED to a PM | 🗣️ ELI5 | 15 min |
| Sat | Anki review + news analysis | 🃏 + 📰 | 20 min |
| Sun | Rest (or casual product thinking while using apps) | 🧩 | 5 min |
