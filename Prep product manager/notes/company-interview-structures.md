# Interview Structures — Amazon & Meta Product Data Scientist (2025–2026)

Sources: [InterviewQuery](https://www.interviewquery.com/guides/amazon-data-scientist), [Prachub](https://prachub.com/interview-guide/amazon-data-scientist-interview-guide), [DataInterview](https://www.datainterview.com/blog/amazon-data-scientist-interview), [Prepfully](https://www.prepfully.com/interview-guides/meta-data-scientist), [igotanoffer](https://igotanoffer.com/blogs/tech/facebook-data-scientist-interview), [DataLemur](https://datalemur.com/blog/meta-data-scientist-interview-guide), [Blind posts 2023–2024](https://www.teamblind.com)

---

## Amazon Data Scientist — Interview Structure

### Overview
- **Total rounds**: 5–8 (recruiter screen → technical screens → final loop)
- **Timeline**: 2–6 weeks
- **Key differentiator**: Leadership Principles are woven into EVERY round, not just behavioral
- **Important**: Loops are fairly unstandardized across orgs — varies by team

### Process Flow

```
1. Recruiter Screen (30 min)
        ↓
2. Technical Screen 1 (45–60 min) — SQL + Statistics
        ↓
3. Technical Screen 2 (45–60 min) — sometimes, depends on team
        ↓
4. Final Virtual Loop (5–6 back-to-back interviews, 45–60 min each)
        ↓
5. Debrief + Decision (within 5 business days)
```

### Final Loop Breakdown (5–6 rounds)

| Round | Focus | LP Evaluation |
|-------|-------|---------------|
| 1 | **SQL + Data Manipulation** — complex queries, optimization, real business scenarios | 2–3 LPs assigned |
| 2 | **Statistics & Experimentation** — A/B test design, hypothesis testing, causal inference | 2–3 LPs assigned |
| 3 | **Applied Problem Solving** — modeling judgment, forecasting, messy business problems | 2–3 LPs assigned |
| 4 | **Product/Business Case** — metrics, root cause analysis, recommendations | 2–3 LPs assigned |
| 5 | **Behavioral Deep Dive** — pure LP stories, often with the Bar Raiser | 2–3 LPs assigned |
| 6 | **Hiring Manager** (sometimes) — fit, career goals, team-specific questions | 2–3 LPs assigned |

### How Amazon Scores

- Each interviewer is assigned 2–3 specific Leadership Principles to evaluate
- They write specific quotes from you as evidence (not paraphrasing)
- Each submits a Hire / No-Hire recommendation
- The **Bar Raiser** (trained interviewer from a different team) has veto power
- You can answer every technical question correctly and still not get the offer if behavioral answers don't align with LPs

### What Amazon DS Interviewers Look For
- SQL, statistics, experimentation, and modeling judgment for messy business problems at scale
- Practical data science — not academic/research focus
- Exact metrics, trade-offs, and YOUR personal contribution
- LP alignment in every answer (even technical ones)

### Amazon-Specific Tips (for Internal Transfer)
- You already know the LP language — use it naturally, don't over-script
- Reference Weblab, internal tools, and real experiments you've supported
- Internal bar may feel higher: they expect you to already "speak Amazon"
- Talk to PMs and DSs on target teams for informational interviews
- Your BIE work directly overlaps with DS work — frame it as "I already do 70% of this"

---

## Meta Data Scientist (Analytics) — Interview Structure

### Overview
- **Total rounds**: 6–7 (recruiter → screens → onsite loop)
- **Timeline**: ~1 week (fast-paced, highly structured)
- **Key differentiator**: 45% of evaluation is product sense and business acumen
- **Important**: DS is embedded directly in product teams, influences strategy

### Process Flow

```
1. Recruiter Screen (20–30 min)
        ↓
2. Initial Technical Screen (45 min) — SQL + product/metrics case mixed
        ↓
3. Onsite Loop (4–5 rounds, 45 min each)
        ↓
4. Team Matching (not formally scored but influences decision)
        ↓
5. Offer
```

### Onsite Loop Breakdown

| Round | Name | What's Tested |
|-------|------|---------------|
| 1 | **Analytical Execution** | Execution-grade data science. Problem is already framed. Output directly informs a product decision. SQL, metrics computation, experiment analysis. |
| 2 | **Analytical Reasoning** | Think like a Meta DS who influences product decisions under uncertainty. Metric definition, experiment design, diagnosing ambiguous problems. |
| 3 | **Product Sense / Case Study** | Define metrics for a product. Diagnose metric changes. Make recommendations. Business acumen. |
| 4 | **Behavioral / Leadership** | Impact stories, cross-functional influence, handling ambiguity, conflict resolution. |
| 5 | **Team Matching** | Not formally scored. Conversation about interests, team fit, what you'd work on. |

### Round Details

#### Analytical Execution (the "can you DO it" round)
- Given a scenario + data description, write SQL or describe analysis approach
- Compute metrics, segment data, analyze experiment results
- Expected to be precise and fast — this is execution, not exploration
- Example: "Here's an experiment on News Feed ranking. Analyze the results and make a recommendation."

#### Analytical Reasoning (the "can you THINK" round)
- Open-ended product/data problems
- Design an experiment from scratch
- Reason about what data you'd need and why
- Handle ambiguity — there's no single right answer
- Example: "How would you measure whether Instagram Reels is cannibalizing Stories?"

#### Product Sense / Case Study
- "How would you measure success for [Meta product]?"
- "DAU for Messenger dropped 10%. Investigate."
- "Should we launch feature X? What data would you need?"
- Must connect analysis to business decisions — not just "here's the data"

#### Behavioral / Leadership
- Impact and ownership stories
- Cross-functional collaboration (working with PMs, engineers)
- Handling disagreement with data
- Scaling yourself / mentoring

### Meta-Specific Tips
- Product sense is 45% of evaluation — don't under-prepare this
- Know Meta's products well: Facebook, Instagram, WhatsApp, Messenger, Threads, Reality Labs
- Think in terms of "billions of users" — scale matters
- Show you can influence product decisions, not just produce analyses
- Speed matters — Meta moves fast, show you can too
- Practice explaining trade-offs concisely (they value communication clarity)

---

## Side-by-Side Comparison

| Dimension | Amazon DS | Meta DS |
|-----------|-----------|---------|
| **Total rounds** | 5–6 in loop | 4–5 in loop |
| **Timeline** | 2–6 weeks | ~1 week |
| **Biggest weight** | Leadership Principles (every round) | Product Sense (45%) |
| **SQL difficulty** | Medium-Hard | Medium-Hard |
| **Stats/Experimentation** | Dedicated round | Split across Execution + Reasoning |
| **Behavioral** | LP-heavy, quote-based scoring | Impact stories, less formulaic |
| **Unique element** | Bar Raiser with veto power | Team matching conversation |
| **Product sense** | Important but not dominant | Dominant (45% of eval) |
| **Coding (Python)** | Sometimes (team-dependent) | Rarely in Analytics track |
| **Standardization** | Low (varies by org) | High (structured process) |
| **Pace** | Slower, more rounds | Fast, compressed timeline |

---

## Prep Priority by Company

### If Amazon is primary target:
1. 🔴 Behavioral / LP stories (every round tests this)
2. 🔴 SQL (dedicated round + woven into others)
3. 🔴 Statistics & Experimentation (dedicated round)
4. 🟡 Product/Business case (1 round)
5. 🟡 Applied modeling judgment (1 round)

### If Meta is primary target:
1. 🔴 Product Sense & Metrics (45% of eval)
2. 🔴 Analytical Execution (SQL + experiment analysis)
3. 🔴 Analytical Reasoning (experiment design, ambiguity)
4. 🟡 Behavioral (1 round, less LP-formulaic)
5. 🟢 Team matching prep (know which teams interest you)

### Shared (prep once, use for both):
- SQL (medium-hard)
- A/B testing / experiment design
- Metric definition and diagnosis
- Behavioral stories (adapt framing per company)

---

## What to Prep Differently

| For Amazon | For Meta |
|-----------|----------|
| Memorize LP definitions, map stories to each | Know Meta products deeply (IG, FB, WhatsApp, Threads) |
| Practice answering with quotable specifics | Practice concise, fast-paced answers |
| Prepare for Bar Raiser pushback | Practice product sense cases (45% weight!) |
| Expect unstandardized format (ask recruiter) | Expect highly structured, predictable format |
| Show "ownership" and "dive deep" in every answer | Show "influence on product decisions" |


---

## Real Interview Experiences (from Blind, 2023–2024)

### Meta DS IC5 — Product Analytics (Nov 2024, Blind)
- Candidate reported all rounds went well EXCEPT Analytical Reasoning
- Got "frozen" and couldn't answer completely in that round
- Other 3 rounds went "exceptionally good" — still didn't get offer
- **Takeaway**: Analytical Reasoning is the make-or-break round. You can't compensate for a bad performance there with strong execution elsewhere.

### Meta DS — Common Pattern from Multiple Posts
- Interviewers push on **contamination, spillovers, and SUTVA violations** when designing experiments for connected users (social network effects)
- They want you to explain why DAU might be the WRONG metric for certain products (e.g., Reels)
- Product judgment with incomplete information is tested repeatedly
- "How would you measure a feature launch?" / "Why did engagement drop?" / "Design an experiment when perfect randomization is hard"

### Amazon DS — Consistent Themes (2023–2024)
- Every interviewer assigned 2–3 specific LPs — they write your EXACT quotes
- You can ace every technical question and still fail if behavioral answers don't align
- Practical data science focus: SQL, statistics, experimentation, modeling judgment for messy problems at scale
- BIE → DS internal transfer is common and doable — "showcase DS skills and pass the tech interview"
- Internal hiring is reportedly easier than external

### BIE → DS Transition (Blind, 2024)
- Multiple posts confirm BIE L5 → DS is a natural lateral move
- Key gap to close: statistical depth (hypothesis testing, causal inference) and Python modeling
- Advantage: you already understand Amazon's data ecosystem, Weblab, and LP culture
- One commenter: "transitioning from a BIE to a DS in one year is doable"

---

## Actual Questions Reported (Meta DS, 2024–2025)

From DataLemur, DataFord, InterviewQuery, and Blind:

### Analytical Reasoning (the hardest round)
- "How would you measure the success of Facebook Marketplace?"
- "Instagram Stories usage is down 10%. How would you investigate?"
- "We want to add a 'Dislike' button to Facebook. How would you measure if it's a good idea?"
- "How would you design an experiment for a feature that affects connected users?"
- "A metric improved but user complaints increased. What's happening?"

### Analytical Execution
- SQL problems with product context (not just syntax — explain WHY)
- "Given this experiment data, analyze results and make a recommendation"
- Compute metrics, segment, identify anomalies
- Expected to be precise and fast — execution, not exploration

### Product Sense
- "How would you define success metrics for Threads?"
- "What metrics would you put on a dashboard for Instagram Reels?"
- "We launched feature X and engagement went up. Should we celebrate?"
- "How do you distinguish correlation from causation in this scenario?"

---

## Emma Ding's Framework — 7 Types of Product Case Questions

Emma Ding (ex-Airbnb DS, now DS interview coach) identifies 7 types of product case questions that appear in DS interviews. Her YouTube channel and blog are highly recommended for product sense prep.

**Source**: [emmading.com](https://www.emmading.com/blog/how-to-ace-the-7-types-of-product-case-interview-questions)

### The 7 Types:

| # | Type | Example Question |
|---|------|-----------------|
| 1 | **Measure Success** | "How would you measure the success of [feature/product]?" |
| 2 | **Diagnose a Metric Change** | "Metric X dropped 15%. Investigate." |
| 3 | **Feature Launch Decision** | "Should we launch this feature? What data do you need?" |
| 4 | **Improve a Product** | "How would you use data to improve [product]?" |
| 5 | **Design an Experiment** | "How would you A/B test [change]?" |
| 6 | **Conflicting Metrics** | "CTR is up but revenue is down. What do you do?" |
| 7 | **Choose Between Options** | "We have two features. Which should we build?" |

### Emma Ding's Approach for Each Type:

#### Type 1: Measure Success
1. Clarify what the product/feature does and who uses it
2. Define the goal (engagement? revenue? retention?)
3. Pick a primary metric (North Star)
4. Add 2–3 supporting metrics
5. Mention guardrail metrics (what shouldn't degrade)
6. Explain how you'd track/instrument

#### Type 2: Diagnose a Metric Change
1. Clarify the metric definition
2. Determine temporal aspect (sudden vs. gradual)
3. Check if other products/features show the same change
4. Segment users by demographics and behavioral features
5. Form hypotheses and validate with data
6. Recommend action

#### Type 3: Feature Launch Decision
1. Define what "success" means for this launch
2. Identify metrics to evaluate
3. Design the experiment (A/B test)
4. Determine sample size and duration
5. Analyze results — statistical AND practical significance
6. Make recommendation with trade-offs

#### Type 4: Improve a Product
1. Understand current state (metrics, user behavior)
2. Identify pain points from data (drop-offs, low engagement areas)
3. Hypothesize improvements
4. Prioritize by expected impact and feasibility
5. Propose how to validate (experiment)

#### Type 5: Design an Experiment
1. State hypothesis clearly
2. Define metrics (primary + guardrails)
3. Choose randomization unit
4. Calculate sample size / duration
5. Address potential issues (novelty, network effects, seasonality)
6. Describe analysis plan

#### Type 6: Conflicting Metrics
1. Understand WHY they conflict (mechanism)
2. Determine which metric is more aligned with long-term user value
3. Check if it's a short-term vs. long-term trade-off
4. Look for a composite metric or OEC that balances both
5. Recommend with clear reasoning

#### Type 7: Choose Between Options
1. Define evaluation criteria (impact, effort, alignment with goals)
2. Estimate impact of each option using available data
3. Consider second-order effects
4. Make a recommendation with clear reasoning
5. Suggest how to validate before full commitment

---

## Emma Ding — Recommended YouTube Videos & Resources

### YouTube Channel: [Emma Ding](https://www.youtube.com/@emmading)
Covers: A/B testing, business case/product sense, SQL, DS projects

### Key Topics to Watch:
- Product case interview walkthrough (measure success)
- How to diagnose a metric drop
- A/B testing interview questions explained
- How to structure product sense answers
- Common mistakes in DS interviews

### Blog Posts (Towards Data Science):
- [Ultimate Guide to Product Case Interviews Part 1](https://towardsdatascience.com/the-ultimate-guide-to-cracking-business-case-interviews-for-data-scientists-part-2-7bc38fbe635f/) — Frameworks for each question type
- [Product Case Interviews Dos and Don'ts](https://towardsdatascience.com/product-case-interviews-dos-and-donts-for-data-scientists-71f9f90b033f/) — Red flags and tips
- [7 Types of Product Case Questions](https://www.emmading.com/blog/how-to-ace-the-7-types-of-product-case-interview-questions) — Complete breakdown

### Paid Course (optional):
- Product Case Interview Pro — 50+ video lessons, 286 questions, cheat sheets
- Note: Only covers product case, not SQL/stats/ML

### Emma Ding's Background:
- Ex-Airbnb Data Scientist and Software Engineer
- Achieved 100% onsite-to-offer rate after being laid off
- Doubled income in 2 months of interviewing
- Now full-time DS interview coach

---

## Updated Prep Resources (Priority Order)

### Free — Start Here
1. **Emma Ding YouTube** — Product case walkthroughs (watch 5–10 videos in Week 3)
2. **LeetCode** — SQL (you have subscription)
3. **DataLemur** — SQL + product sense questions
4. **StatQuest YouTube** — Statistics concepts
5. **Your experimentation book** — A/B testing depth

### Paid (if you want more structure)
1. **InterviewQuery** ($) — DS-specific questions with solutions, good for Meta prep
2. **DataInterview** ($) — Product DS focused, company-specific guides
3. **Emma Ding Product Case Course** ($$) — If product sense is your weakest area
4. **Exponent** ($) — Video walkthroughs, mock interviews

### Free Blogs & Guides
- DataLemur Meta DS guide (31 leaked questions)
- InterviewQuery product DS questions
- Prachub company-specific guides
- Towards Data Science (Emma Ding's articles)
