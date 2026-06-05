# Onboarding Prompt for Antigravity IDE (or any AI IDE)

## What This Is

This is the exact message your friend should paste into Antigravity the FIRST time they open this workspace. It tells the AI agent to:
1. Read and understand the full repo structure
2. Set up any IDE-specific configuration (like custom instructions)
3. Create a personal learning log for the user
4. Start coaching

---

## COPY EVERYTHING BELOW AND PASTE INTO ANTIGRAVITY CHAT:

---

I've just opened a Product Data Scientist interview prep workspace. I need you to do the following:

### Step 1: Read the master instructions
Read the file `INSTRUCTIONS.md` in the root of this workspace. It contains your complete role definition as my interview coach, all coaching rules, the file structure, multi-user setup, and frameworks to enforce.

### Step 2: Understand the file structure
Scan the directory tree so you know where everything is:
- `plan/` — my 12-week prep plan, podcast prompts, fun study methods
- `frameworks/` — reusable frameworks (experiment design, metric diagnosis, STAR, AARRR)
- `questions/` — 150+ practice questions organized by category (statistics, experimentation, product-sense, python-coding, behavioral, ai-product, estimation)
- `notes/learning-logs/` — per-user progress tracking (each person gets their own file)
- `resources/` — reading list, YouTube channels, book recommendations
- `notes/` — research on interview structures, trends, company-specific intel

### Step 3: Set up persistent instructions (if supported)
If this IDE supports custom instructions, system prompts, or rules that persist across sessions, set up the contents of `INSTRUCTIONS.md` as those persistent instructions so you remember your role every time I open a new chat. If not supported, just remember to re-read `INSTRUCTIONS.md` at the start of each session when I say "let's practice."

### Step 4: Create my personal learning log
Ask me my name. Then check if a file `notes/learning-logs/{my_name}_learning_logs.md` exists.
- If it exists: read it to understand my current level and gaps
- If it doesn't exist: create it using this template:

```markdown
# Learning Log — {name}

This file tracks concepts {name} got wrong, didn't know, or needs more practice on.

---

## Profile
- Current role: 
- Target: L5 Product Data Scientist (FAANG)
- Strengths: 
- Growth areas: 

---

## Gaps Identified

(entries will be added as we practice)

---

## Patterns & Focus Areas

(will be updated as gaps accumulate)
```

Then ask me about my background (current role, strengths, growth areas) and fill in the Profile section.

### Step 5: Start coaching
Ask me what I want to practice today. Offer these options:
- Product sense / metrics question
- Statistics / probability question
- Experiment design question
- Metric diagnosis question
- Behavioral (STAR) question
- Full mock interview simulation

From here on, follow all the rules in `INSTRUCTIONS.md` — enforce structure, log my gaps, score my answers, and push me to improve.

---

## END OF ONBOARDING PROMPT

---

## After the First Time

Your friend never needs to paste this again. On subsequent sessions, they just say:

> "Let's practice"

And the AI should read their learning log and pick up where they left off. If it doesn't remember, they can say:

> "Read INSTRUCTIONS.md and my learning log at notes/learning-logs/{name}_learning_logs.md, then let's practice"

---

## Troubleshooting

| Problem | Solution |
|---------|----------|
| AI doesn't read INSTRUCTIONS.md | Say: "Read the file INSTRUCTIONS.md and follow it" |
| AI doesn't remember between sessions | Say: "Read my learning log at notes/learning-logs/{name}_learning_logs.md" |
| AI doesn't update learning log | Say: "Update my learning log with the gaps from this session" |
| AI doesn't enforce structure | Say: "Remind me to start with 'I'll structure this as...' before every answer" |
