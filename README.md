# Product Data Scientist Prep

AI-powered interview prep for Product Data Scientist roles at FAANG companies (Meta, Google, Amazon, Netflix, Apple).

Built to work with **any AI IDE** — Kiro, Antigravity, Cursor, or any LLM with file access.

---

## What's Inside

| Folder | What |
|--------|------|
| `plan/` | structured plan, podcast prompts (14 episodes), fun study methods |
| `frameworks/` | Reusable frameworks: experiment design, metric diagnosis, STAR, AARRR |
| `questions/` | 150+ practice questions across 7 categories |
| `notes/` | Interview research, company-specific intel, per-user learning logs |
| `resources/` | Reading list, YouTube channels, book recommendations |

## Question Categories

- **Statistics & Probability** — hypothesis testing, Bayes, distributions (30 questions)
- **Experimentation / A/B Testing** — design, power, pitfalls, causal inference (30 questions)
- **Product Sense & Metrics** — metric definition, diagnosis, trade-offs (28 questions)
- **Python Coding** — pandas, statistical analysis, experiment analysis (24 questions)
- **Behavioral** — STAR format, Amazon LPs (16 questions)
- **AI/ML Product Thinking** — AI-first design, failure modes (22 questions)
- **Estimation** — Fermi problems, market sizing (10 questions)

---

## Quick Start

### Using Kiro (AWS AI IDE)
1. Open this folder in Kiro
2. The steering files (`.kiro/steering/`) auto-load — just say "let's practice"
3. Your learning log updates automatically via hooks

### Using Antigravity (Google) or any other AI IDE
1. Clone this repo and open in your IDE
2. Copy the onboarding prompt from `ONBOARDING-PROMPT.md` into your first chat
3. The AI will set itself up, ask your name, create your learning log, and start coaching
4. After first time: just say "let's practice"

### Using ChatGPT / Claude / Gemini (no file access)
1. Copy the system prompt from `SYSTEM-PROMPT-FOR-OTHER-LLMS.md`
2. Paste at the start of each session
3. Reference question files manually

---

## Multi-User Support

Multiple people can share this repo. Each person gets their own learning log:





## Repo Structure

```
├── plan/                      # 12-week structured prep plan
├── frameworks/                # Reusable frameworks and templates
│   ├── experimentation-design.md
│   ├── metric-diagnosis.md
│   ├── star-method.md
│   ├── metrics-aarrr.md
│   └── ...
├── questions/                 # Practice questions by category
│   ├── statistics/            # Probability, hypothesis testing, distributions
│   ├── experimentation/       # A/B testing, causal inference
│   ├── product-sense/         # Metrics, diagnosis, trade-offs
│   ├── python-coding/         # pandas, statistical analysis
│   ├── behavioral/            # STAR stories, LPs
│   ├── ai-product/            # AI/ML product thinking
│   └── estimation/            # Market sizing (lower priority)
├── answers/                   # Drafted answers for review
├── case-studies/              # Company deep-dives
├── notes/                     # Study notes and research
├── resources/                 # Book summaries, links
└── mock-sessions/             # Mock interview logs with Kiro
```

## How to Use with Kiro
- **Mock interview**: "Mock me on experimentation" or "Give me a product sense question"
- **Review answers**: Save drafts in `answers/` and ask Kiro to critique
- **Explain concepts**: "Explain CUPED" or "Walk me through power analysis"
- **Timed practice**: "Give me a 15-min stats question" — Kiro will time and score
- **Full loop simulation**: "Simulate a full DS interview loop"

## Interview Categories (by weight)

| Category | Weight | Your Readiness |
|----------|--------|---------------|
| SQL | High | ✅ Strong (maintain with LeetCode) |
| Statistics & Probability | High | 🟡 Needs depth |
| Experimentation / A/B Testing | High | 🟡 Book + BIE experience = strong foundation |
| Product Sense & Metrics | High | 🟡 Need to reframe from DS angle |
| Behavioral (LPs) | High | 🟡 Need story bank |
| Python Coding | Medium | 🟡 Need practice |
| AI/ML Product Thinking | Medium | 🟡 New category |
