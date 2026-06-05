# Podcast Episode Prompts — Gemini NotebookLM

Generate one episode per topic using Gemini's podcast/audio feature. Listen on walks, commutes, or downtime. Each prompt is designed to produce a ~15–20 min conversational episode packed with examples.

---

## How to Use
1. Copy one prompt into Gemini
2. Generate the audio/podcast
3. Listen during your walk that day
4. Follow the suggested schedule (matches your 12-week plan)

---

## Episode 1: A/B Testing Fundamentals — The Mental Model

**Prompt:**

> Create a conversational podcast episode explaining A/B testing for someone who works with data but hasn't designed experiments from scratch. Assume the listener learns best through concrete examples and analogies — not abstract definitions.
>
> Start with a simple analogy: A/B testing is like a taste test at a grocery store. You give half the people the old recipe and half the new recipe, and see which one they prefer. That's it at its core.
>
> Then build up with real product examples:
>
> Example 1: Amazon changes the "Add to Cart" button from orange to green. They show the orange button to 500,000 users and the green button to 500,000 users. After 2 weeks, they compare purchase rates. Walk through what happens step by step.
>
> Example 2: Netflix tests a new thumbnail image for a show. Group A sees the old thumbnail, Group B sees the new one. They measure click-through rate. The new thumbnail gets 3% more clicks. Is that enough to ship? Discuss.
>
> Example 3: Spotify tests a new "Discover Weekly" algorithm. Walk through why you can't just launch it to everyone and compare this week to last week (seasonality, other changes happening simultaneously).
>
> Explain these concepts through the examples above:
> - Control group vs. treatment group (use the Amazon button example)
> - Why randomization matters (use a restaurant analogy — if you only give the new dish to regulars, you can't tell if it's the dish or the customer type)
> - Statistical significance in plain language: "If I flip a coin 10 times and get 7 heads, is the coin unfair? Probably not. But if I flip it 10,000 times and get 7,000 heads, something is definitely going on." That's significance — being confident the difference isn't just luck.
> - P-value: "The p-value is the probability that you'd see this result (or more extreme) if there was actually NO real difference. A p-value of 0.03 means there's only a 3% chance this result is just noise."
> - Practical significance vs. statistical significance: "The green button gets 0.01% more clicks. Statistically significant with 1 million users. But is it worth the engineering effort to change? Probably not."
>
> End with a summary: "An A/B test is just a fair comparison. You change ONE thing, keep everything else the same, wait long enough, and check if the difference is real or just noise."
>
> Keep it conversational, slow-paced, and repeat key concepts. The listener is smart but new to this — they need examples, not jargon. Target 18 minutes.

**Listen during:** Week 1

---

## Episode 2: The OEC — Choosing Your One Metric That Matters

**Prompt:**

> Create a podcast episode about the Overall Evaluation Criterion (OEC) concept from experimentation. The listener learns best through examples and stories, so use lots of them. Go slow and repeat key ideas.
>
> Start with a story: "Imagine you're a chef and you change your restaurant's menu. How do you know if the change was good? You could look at: number of customers, average bill size, tips, Yelp reviews, food waste, staff happiness. But if customers went up and tips went down and reviews stayed flat — did it work? You need ONE primary metric to judge by. That's your OEC."
>
> Example 1 — Search Engine (like Google):
> - Bad OEC: "Number of searches per user" — why? Because if search is BAD, people search MORE (they can't find what they want). More searches could mean worse quality.
> - Better OEC: "Successful sessions" — user searches, clicks a result, and doesn't come back to search again within 30 seconds. That means they found what they needed.
> - Walk through why this is counterintuitive but correct.
>
> Example 2 — Netflix:
> - Bad OEC: "Hours watched" — why? Because someone might watch 5 hours of mediocre content and then cancel. Hours watched doesn't capture satisfaction.
> - Better OEC: "Retention rate" or "Percentage of users who watch something they rate 4+ stars within their first week"
> - Discuss the tension: short-term engagement vs. long-term retention.
>
> Example 3 — Uber:
> - The OEC needs to balance BOTH sides of the marketplace. "Rides completed" is good but misses driver satisfaction.
> - Walk through how a two-sided marketplace makes OEC selection harder.
>
> Then explain guardrail metrics with an analogy: "Your OEC is like your destination on a road trip. Guardrail metrics are the speed limit and fuel gauge — you don't optimize for them, but if you violate them, you stop the trip."
> - Example: You're optimizing for engagement (OEC). Your guardrails are: revenue doesn't drop more than 1%, page load time doesn't increase more than 200ms, customer support tickets don't spike.
>
> End with a practical framework: "To choose an OEC, ask: (1) Does this metric move when users get more value? (2) Can it be gamed? (3) Can I measure it in the timeframe of my experiment? (4) Does it align with long-term business health?"
>
> Keep it slow, conversational, example-heavy. Target 17 minutes.

**Listen during:** Week 1-2

---

## Episode 3: When Experiments Go Wrong — Pitfalls and Traps

**Prompt:**

> Create a podcast episode about the most common ways A/B tests fail or mislead you. Make it feel like "horror stories from the experimentation lab." The listener learns best through vivid examples and stories.
>
> Pitfall 1 — Peeking (checking results too early):
> Story: "A PM at a startup checks the A/B test dashboard every morning. On day 3, the new feature shows +15% conversion. 'Ship it!' they say. But by day 14, the effect has shrunk to +2% and is no longer significant. What happened?"
> Explain: Early results are noisy. It's like judging a baseball player's season average after 5 at-bats. With small samples, random streaks look like real patterns. The more times you check, the more likely you'll see a false positive. Analogy: "If you flip a coin 10 times, getting 8 heads isn't that weird. But if you flip it 1000 times and get 800 heads, THAT'S real."
>
> Pitfall 2 — Novelty Effect:
> Story: "Facebook adds a new reaction button. In the first week, usage is through the roof — everyone's trying it. The PM celebrates. But by week 4, usage drops 80%. People were just curious."
> Explain: Users react to NEWNESS, not necessarily to the feature being good. Solution: run experiments for at least 2-3 weeks. Compare week 1 vs. week 3 behavior.
>
> Pitfall 3 — Primacy Effect (the opposite):
> Story: "YouTube changes its homepage layout. In week 1, engagement drops 5%. The team panics. But by week 4, engagement is UP 3%. Users just needed time to adjust to the new layout."
> Explain: People resist change initially. If you kill experiments too early, you might kill good features.
>
> Pitfall 4 — Simpson's Paradox:
> Story: "A hospital has two treatments. Treatment A has a higher success rate overall. But when you look at severe cases separately and mild cases separately, Treatment B is better in BOTH groups. How is that possible?"
> Explain with a product example: "Your new feature shows +5% engagement overall. But when you segment: mobile users (80% of traffic) show -2%, and desktop users (20% of traffic) show +40%. The overall number is misleading because desktop users are a small but very active group pulling the average up."
>
> Pitfall 5 — Twyman's Law:
> "Any figure that looks interesting or different is usually wrong." Story: "Your experiment shows a +50% improvement. Before celebrating, check: Did logging break? Did a bot inflate numbers? Did the control group have a bug? The more surprising the result, the more likely it's a data error."
>
> Pitfall 6 — Network Effects / SUTVA Violation:
> Story: "You're testing a new messaging feature on WhatsApp. You put User A in treatment (they get the feature) and User B in control. But User A messages User B using the new feature. Now User B's experience is affected even though they're in the control group."
> Explain: This violates the assumption that one user's treatment doesn't affect another. Solution: randomize at the group/cluster level, not individual level.
>
> End with: "The lesson is: getting numbers is easy. Getting numbers you can TRUST is hard. Always be skeptical of your own results."
>
> Make it engaging, story-driven, slow-paced. Target 20 minutes.

**Listen during:** Week 2-3

---

## Episode 4: Product Metrics — How Data Scientists Think About Measurement

**Prompt:**

> Create a podcast episode about how product data scientists think about metrics. The listener is a data professional who builds dashboards but wants to think more strategically about WHICH metrics matter and WHY. Use lots of real company examples. Go slow, repeat key ideas.
>
> Start with an analogy: "Metrics are like vital signs for a product. A doctor doesn't just check your temperature — they check heart rate, blood pressure, oxygen levels. Each tells a different story. And if your temperature is fine but your blood pressure is dangerously high, you still have a problem."
>
> Section 1 — The AARRR Funnel (explain with Spotify example):
> - Acquisition: How do people find Spotify? (ads, word of mouth, app store) Metric: new sign-ups per week
> - Activation: Do they have a good first experience? Metric: "Did they create a playlist or listen to 3+ songs in their first session?"
> - Retention: Do they come back? Metric: Day 7 retention, Day 30 retention, monthly active users
> - Revenue: Do they pay? Metric: free-to-premium conversion rate, ARPU
> - Referral: Do they tell friends? Metric: invite sends, viral coefficient
> Walk through each stage slowly with the Spotify example.
>
> Section 2 — North Star Metrics (3 examples):
> - Airbnb: "Nights booked" — captures value for both guests AND hosts in one number
> - Slack: "Messages sent in channels with 3+ people" — not just messages (could be spam), specifically collaborative messages
> - Amazon: "Purchase frequency" — not just revenue (could be one big purchase), but how often people come back
> For each, explain WHY it's a good North Star: it moves when users get value, it's hard to game, it predicts long-term business health.
>
> Section 3 — Metric Trees (use Uber example):
> "Total rides completed" breaks down into:
> - Rides = Riders x Rides per rider
> - Rides per rider = Sessions x Conversion rate
> - Conversion rate depends on: wait time, price, availability
> "When total rides drop, you look at the tree to find WHERE the problem is. Is it fewer riders? Or same riders taking fewer rides? Or same sessions but lower conversion?"
> Walk through this decomposition step by step.
>
> Section 4 — Vanity Metrics vs. Actionable Metrics:
> - Vanity: "Total downloads" (includes people who downloaded and never opened the app)
> - Actionable: "Weekly active users" (people actually using it)
> - Vanity: "Page views" (could be bots, could be confused users clicking around)
> - Actionable: "Successful task completions"
> Rule of thumb: "If the metric can go up while the user experience gets worse, it's probably a vanity metric."
>
> Section 5 — Leading vs. Lagging:
> - Lagging: Revenue (tells you what already happened)
> - Leading: Activation rate (predicts future revenue)
> Analogy: "A lagging indicator is like looking in the rearview mirror. A leading indicator is like looking through the windshield."
>
> Keep it conversational, example-heavy, slow-paced. Repeat key frameworks. Target 18 minutes.

**Listen during:** Week 3

---

## Episode 5: Diagnosing a Metric Drop — The Detective Framework

**Prompt:**

> Create a podcast episode that teaches how to investigate when a product metric drops unexpectedly. Make it feel like a detective story. The listener learns best through detailed walkthroughs of real scenarios.
>
> Start with the scenario: "It's Monday morning. You're a data scientist at Instagram. Your PM sends a Slack message: 'Hey, Story views dropped 12% week-over-week. Can you look into this?' What do you do?"
>
> Walk through the FULL investigation, step by step, thinking out loud:
>
> Step 1 — Don't panic. Verify the data first.
> "Before I investigate the product, I investigate the DATA. Did our logging break? Did we deploy a new tracking SDK? Did a data pipeline fail over the weekend?"
> Example: "I once saw a 30% drop in a metric that turned out to be a timezone change in our data warehouse. The data was fine — it was just shifted by 8 hours and the daily aggregation looked wrong."
> Rule: "Twyman's Law — any figure that looks interesting is usually wrong. Check the boring stuff first."
>
> Step 2 — Segment the data.
> "I break down the 12% drop by: platform (iOS vs. Android vs. Web), geography (US vs. Europe vs. Asia), user type (new vs. returning), user cohort (signed up this month vs. 6 months ago)."
> Example: "I find that iOS dropped 20% but Android is flat. Now I know it's an iOS-specific issue. That narrows my investigation enormously."
> Another example: "Or maybe ALL platforms dropped equally — that suggests a content or algorithm issue, not a technical one."
>
> Step 3 — Check the timeline.
> "When exactly did the drop start? Was it sudden (cliff) or gradual (slope)?"
> Example: "If it started exactly on Thursday at 2pm, I check: what deployed on Thursday? Any app updates? Any server changes?"
> Example: "If it's been gradually declining for 3 weeks, it's probably not a bug — it might be a seasonal trend or a slow content quality issue."
> "I also check: did anything external happen? Holiday? Competitor launch? News event?"
>
> Step 4 — Form hypotheses (rank by likelihood).
> "Based on what I've found so far (iOS-specific, started Thursday), my hypotheses are:
> 1. iOS app update broke something in Stories rendering (most likely — timing matches)
> 2. iOS 18 update changed notification permissions (possible — check iOS update rollout dates)
> 3. Content quality declined (unlikely — would affect all platforms)
> 4. Seasonal effect (unlikely — too sudden)"
>
> Step 5 — Validate each hypothesis.
> "For hypothesis 1: I check crash logs for the iOS Stories feature. I check if Story CREATION also dropped (if people can't view, maybe they also can't create). I check if the drop correlates exactly with the app version rollout."
> "For hypothesis 2: I check if the drop correlates with iOS 18 adoption rate. I check notification opt-in rates before and after."
>
> Step 6 — Recommend action.
> "I found that the iOS app update introduced a bug where Stories take 3 seconds longer to load. Users are abandoning before they load. My recommendation: hotfix the loading issue. Expected recovery: full metric recovery within 1 week of fix deployment."
>
> End with the framework summary: "Verify data → Segment → Timeline → Hypothesize → Validate → Recommend. Always start with 'is the data right?' and always end with 'what should we DO about it?'"
>
> Make it feel like a real investigation story. Go slow. The listener should be able to follow along and internalize the framework. Target 18 minutes.

**Listen during:** Week 3-4


---

## Episode 6: Behavioral Interview Mastery — Telling Your Story

**Prompt:**

> Create a podcast episode about how to ace behavioral interviews for data science roles at big tech companies. The listener is a technical person (Business Intelligence Engineer at Amazon) who is analytically strong but struggles with storytelling. Go slow, use examples, and make it practical.
>
> Start with WHY behavioral interviews matter:
> "At Amazon, you can answer every SQL and statistics question perfectly and still get rejected. Why? Because every interviewer is assigned 2-3 Leadership Principles to evaluate. They write down your EXACT words as evidence. If your stories don't demonstrate those principles, it's a no-hire."
>
> Explain STAR with a full example:
> "Let's say the question is: 'Tell me about a time you used data to influence a decision.'
>
> BAD answer (no structure): 'Yeah so there was this project where we had some data issues and I worked with the team and we figured it out and it went well.'
>
> GOOD answer (STAR):
> - Situation (15 sec): 'Last year, our team was deciding whether to invest in a new recommendation feature for our product page. The PM wanted to build it based on customer feedback alone.'
> - Task (15 sec): 'As the BIE, I was responsible for providing data-driven input. I believed we needed quantitative validation before committing 3 engineers for a quarter.'
> - Action (60 sec): 'I pulled 6 months of clickstream data and built a cohort analysis showing that users who engaged with similar recommendations on other pages had 23% higher purchase rates. I then designed a simple A/B test proposal using Weblab, presented it to the PM and engineering lead, and convinced them to run a 2-week experiment before full commitment.'
> - Result (30 sec): 'The experiment showed a 12% lift in add-to-cart rate. We shipped the feature, and it generated an estimated $1.4M in incremental annual revenue. The PM later told me this changed how she approaches feature decisions.'"
>
> Walk through WHY this works: specific, quantified, shows personal contribution ("I" not "we"), demonstrates the LP (Dive Deep + Have Backbone).
>
> Then give 3 more example stories a BIE might tell:
>
> Example 2 — Ownership: "A dashboard I built revealed a data quality issue in our pipeline that was causing incorrect inventory forecasts. Nobody owned this problem. I took it upon myself to..."
>
> Example 3 — Bias for Action: "We had incomplete data about customer churn but needed to make a decision within a week. Rather than waiting for perfect data, I..."
>
> Example 4 — Earn Trust: "I disagreed with my manager's interpretation of an A/B test result. The test showed positive results, but I noticed the control group had a bug that deflated their numbers. I..."
>
> Common mistakes to avoid:
> - "We did X" — interviewer wants YOUR contribution, not the team's
> - Spending 2 minutes on Situation and 30 seconds on Action (flip this ratio)
> - No quantified result ("it went well" vs. "it saved $500K annually")
> - Story doesn't match the question (they ask about failure, you tell a success story)
> - Going over 2.5 minutes (practice with a timer)
>
> End with: "Build a bank of 8-10 stories. Each story should be flexible enough to answer 2-3 different questions. Practice them out loud until they're under 2 minutes. The goal is to sound natural, not rehearsed."
>
> Keep it slow, practical, example-heavy. Target 18 minutes.

**Listen during:** Week 4

---

## Episode 7: Causal Inference — When You Can't Run an Experiment

**Prompt:**

> Create a podcast episode explaining causal inference methods for product data scientists. The listener is smart but new to this topic — they need intuition through examples, not math. Go very slow. Repeat key ideas. Use analogies.
>
> Start with WHY you sometimes can't A/B test:
> "Imagine you're a DS at Uber and you want to know: does surge pricing cause riders to leave the platform long-term? You can't randomly assign surge pricing to some users and not others — that's unfair and possibly illegal. So how do you figure out the causal effect?"
>
> Another example: "You're at Instagram and you want to know: does posting Reels make creators more successful? You can't randomly FORCE some creators to post Reels. Creators who post Reels might just be more motivated in general. How do you separate the effect of Reels from the effect of being a motivated creator?"
>
> Method 1 — Difference-in-Differences (with detailed example):
> Analogy: "Imagine two identical twin cities. One gets a new highway, the other doesn't. You compare traffic BEFORE and AFTER in both cities. The difference in the differences tells you the effect of the highway."
> Product example: "Uber launches a new driver incentive program in Dallas but not in Houston. Both cities had similar growth trends before. After the launch, Dallas grows 15% faster than Houston. The 15% difference is likely caused by the incentive program."
> Walk through step by step: "Before launch: Dallas growing 5%/month, Houston growing 5%/month. After launch: Dallas growing 20%/month, Houston growing 8%/month. Difference-in-differences: (20-5) - (8-5) = 12%. The incentive program caused ~12% extra growth."
> Key assumption: "Both cities would have continued on the same trend WITHOUT the intervention. If something else happened in Dallas (like a tech company moving there), this breaks."
>
> Method 2 — Regression Discontinuity (with detailed example):
> Analogy: "Imagine a school gives scholarships to students who score above 80 on a test. Students who scored 79 and 81 are basically identical — the only difference is the scholarship. By comparing outcomes for students just below and just above 80, you can estimate the effect of the scholarship."
> Product example: "Amazon gives Prime free trial to users who spend above $100 in their first month. Users who spent $99 and $101 are basically the same. By comparing their long-term behavior, you can estimate the causal effect of Prime trial on retention."
> Walk through: "You plot spending on X-axis and retention on Y-axis. If there's a JUMP in retention right at the $100 threshold, that jump is caused by the Prime trial."
>
> Method 3 — Propensity Score Matching (with detailed example):
> Analogy: "You want to know if exercise causes weight loss. You can't randomly assign people to exercise. But you CAN find pairs of people who are similar in every way (age, diet, job, genetics) except one exercises and one doesn't. Then you compare their weight loss."
> Product example: "You want to know if using the 'Save for Later' feature on Amazon causes higher purchase rates. You find pairs of users who are similar (same browsing history, same demographics, same purchase history) but one uses Save for Later and one doesn't. Then you compare their purchase rates."
> Limitation: "This only works if you can measure ALL the important differences. If there's something you can't measure (like motivation), it can still bias your results."
>
> Method 4 — Synthetic Control (with detailed example):
> Analogy: "You want to know what would have happened to California's economy if a specific policy hadn't been enacted. You can't go back in time. But you CAN create a 'synthetic California' by combining other states (30% Texas + 20% New York + 50% Oregon) that together look like California did before the policy. Then you compare real California to synthetic California after the policy."
> Product example: "Netflix launches a new pricing tier in Brazil. To estimate the effect, they create a 'synthetic Brazil' from a weighted combination of other Latin American countries that had similar trends before the launch."
>
> End with a decision framework:
> "When should you use each method?
> - Diff-in-diff: When you have a natural 'treatment' and 'control' group with parallel trends before
> - Regression discontinuity: When there's a clear threshold/cutoff that determines treatment
> - Propensity matching: When you have rich data about users but no natural experiment
> - Synthetic control: When you have one treated unit (like a country or city) and need to construct a counterfactual"
>
> Keep it very slow, analogy-heavy, and repeat the core idea of each method multiple times. Target 22 minutes.

**Listen during:** Week 4-5

---

## Episode 8: Meta's DS Interview — What They Actually Test

**Prompt:**

> Create a podcast episode specifically about Meta's Product Data Scientist (Analytics) interview process. The listener is preparing for this interview and wants to know exactly what to expect. Use examples of actual questions and walk through how to answer them.
>
> Start with the big picture: "Meta's DS interview has one thing that makes it different from every other company: 45% of your evaluation is product sense and business acumen. You can be a statistics wizard, but if you can't connect your analysis to a product decision, you won't get hired."
>
> Walk through each round with examples:
>
> Round 1 — Analytical Execution:
> "This round tests: can you DO the analysis when the problem is already framed?"
> Example question: "Here's data from an A/B test on Instagram's Explore page. Group A saw the old algorithm, Group B saw the new one. Here are the metrics. Analyze the results and make a recommendation."
> What they want: "Fast, precise analysis. Compute the metrics correctly. Notice if something looks off. Make a clear recommendation. Don't ramble."
> Walk through how you'd answer: "First I'd check if the groups are balanced. Then I'd look at the primary metric. Then I'd check guardrails. Then I'd segment by user type. Then I'd make a recommendation with caveats."
>
> Round 2 — Analytical Reasoning (THE MAKE-OR-BREAK ROUND):
> "This is where most people fail. It tests: can you THINK like a DS who influences product decisions under uncertainty?"
> Example question: "How would you measure whether Instagram Reels is cannibalizing Stories?"
> Walk through the thinking: "First, what does 'cannibalization' mean here? Users spending time on Reels INSTEAD of Stories, not in addition to. So I'd look at: (1) Did Stories usage decline after Reels launched? (2) Among users who adopted Reels heavily, did their Stories usage drop more than users who didn't adopt Reels? (3) But wait — maybe heavy Reels users are just more active overall. I need to control for overall activity level. (4) I could use a diff-in-diff approach: compare Stories usage before/after Reels launch for heavy Reels adopters vs. light adopters, controlling for their pre-Reels activity levels."
> "See how that answer shows THINKING, not just a formula? That's what this round tests."
>
> Another example: "We want to add a 'Dislike' button to Facebook. How would you measure if it's a good idea?"
> Walk through: "Good for whom? Users who dislike content? Users whose content gets disliked? The platform's content ecosystem? I'd need to define success carefully..."
>
> Round 3 — Product Sense:
> Example question: "How would you define success metrics for Threads?"
> Walk through: "I'd start with: what's Threads trying to be? A public conversation platform competing with Twitter/X. So success means: (1) Users are having conversations (not just posting into the void), (2) Users are coming back (retention), (3) Content quality is high enough to attract more users (growth). My North Star: 'Daily active users who both post AND reply.' Supporting metrics: DAU, posts per user, reply rate, D7 retention. Guardrails: hate speech rate, user reports, creator burnout."
>
> Round 4 — Behavioral:
> "Less formulaic than Amazon. They want impact stories. 'Tell me about a project you owned end-to-end. What was the impact?'"
> Tip: "Quantify everything. 'I influenced a $2M decision' is better than 'I helped the team make a decision.'"
>
> End with Meta-specific tips:
> - Know their products: Facebook, Instagram, WhatsApp, Messenger, Threads, Reality Labs
> - Practice explaining why obvious metrics might be WRONG
> - Speed matters — Meta moves fast, show you can think quickly
> - The process takes ~1 week total — it's compressed and intense
>
> Keep it practical, example-heavy, slow-paced. Target 20 minutes.

**Listen during:** Week 5

---

## Episode 9: Amazon's DS Interview — Leadership Principles and the Bar Raiser

**Prompt:**

> Create a podcast episode about Amazon's Data Scientist interview process, specifically for someone who is currently a BIE at Amazon looking to transfer internally to DS. Use lots of examples and insider knowledge. Go slow.
>
> Start with the unique thing about Amazon: "At most companies, the technical interview is king. At Amazon, you can ace every technical question and still get rejected. Why? Because of Leadership Principles. Every single interviewer — even the one asking you SQL questions — is assigned 2-3 specific LPs to evaluate. They write down your EXACT quotes. Not a summary. Your actual words."
>
> Explain the Bar Raiser: "One of your 5-6 interviewers is a 'Bar Raiser.' This is a specially trained interviewer from a DIFFERENT team. They have veto power. Even if 4 out of 5 interviewers say hire, the Bar Raiser can say no. Their job is to ensure every new hire raises the average quality of the team."
>
> Walk through a typical DS loop with examples:
>
> Round 1 — SQL + Data Manipulation:
> Example: "You have a table of user orders with columns: user_id, order_date, order_amount, product_category. Write a query to find users whose average order value increased month-over-month for 3 consecutive months."
> "But here's the Amazon twist: while you're writing SQL, the interviewer asks: 'Tell me about a time you dove deep into data to find an insight that wasn't obvious.' You need to answer the LP question AND finish the SQL. They're testing both simultaneously."
>
> Round 2 — Statistics & Experimentation:
> Example: "You ran a Weblab experiment testing a new search ranking algorithm. The treatment group shows +3% in clicks but -1% in purchases. What do you recommend?"
> Walk through: "I'd first check if both results are statistically significant. Then I'd think about which metric matters more for long-term user value. Clicks are a leading indicator but purchases are the actual business outcome. I'd investigate: are users clicking more but on less relevant results? Maybe the new algorithm is more 'clickbaity' but less useful..."
> LP tested: Dive Deep, Customer Obsession
>
> Round 3 — Applied Problem Solving:
> Example: "A business team asks you to predict which products will go out of stock next week. You have historical sales data, inventory levels, and supplier lead times. How would you approach this?"
> "They're not looking for a perfect ML solution. They want to see: Can you frame a messy business problem? Do you ask clarifying questions? Do you start simple before going complex?"
> LP tested: Bias for Action, Invent and Simplify
>
> Round 4 — Product/Business Case:
> Example: "Prime Video engagement is flat quarter-over-quarter. The VP asks you to investigate. What do you do?"
> Walk through the metric diagnosis framework with Amazon-specific context.
> LP tested: Customer Obsession, Ownership
>
> Round 5 — Behavioral (often the Bar Raiser):
> "This is pure LP stories. They'll ask 2-3 questions in 45 minutes and go DEEP on each one."
> Example: "Tell me about a time you disagreed with a stakeholder and how you handled it."
> "They'll follow up: 'What data did you use? What was the outcome? What would you do differently? How did the other person react?' They dig until they find the truth."
>
> Tips for internal transfer:
> - "You already speak LP language — use it naturally, don't over-script"
> - "Reference Weblab, QuickSight, Redshift, internal tools — show you know the ecosystem"
> - "Frame your BIE work as DS work: 'I already define metrics, run experiment analysis, and influence product decisions. The gap is in statistical modeling depth, which I've been building.'"
> - "Talk to DSs on your target team BEFORE applying. Ask: 'What does a typical week look like? What's the biggest challenge?' Use their answers in your interviews."
> - "Internal transfers still go through the full loop. Don't assume it's easier."
>
> Keep it slow, practical, insider-focused. Target 20 minutes.

**Listen during:** Week 5-6

---

## Episode 10: Statistical Power and Sample Size — The Intuition

**Prompt:**

> Create a podcast episode that builds intuition for statistical power and sample size without any math formulas. The listener is smart but learns best through analogies and examples. Go very slow. Repeat key ideas multiple times with different examples.
>
> Start with the core analogy: "Statistical power is like a metal detector's sensitivity. If you're looking for a gold nugget (a real effect), your metal detector needs to be sensitive enough to find it. A tiny gold nugget (small effect) needs a very sensitive detector (large sample size). A huge gold nugget (large effect) can be found with a cheap detector (small sample size)."
>
> Build up concept by concept:
>
> Concept 1 — What is power?
> "Power is the probability that your experiment will detect a real effect IF one actually exists. Standard is 80%. That means: if the new feature truly is better, you have an 80% chance of your experiment showing it's better."
> "The scary flip side: with 80% power, there's still a 20% chance you MISS a real improvement. You'd conclude 'no effect' when there actually was one."
> Example: "Imagine you have a coin that's slightly biased — it lands heads 52% of the time instead of 50%. If you flip it 10 times, you probably won't notice it's biased. But if you flip it 10,000 times, the bias becomes obvious. That's power — having enough 'flips' (sample size) to detect the bias (effect)."
>
> Concept 2 — Minimum Detectable Effect (MDE):
> "Before running an experiment, you decide: what's the SMALLEST improvement worth detecting? This is your MDE."
> Example: "Your checkout conversion rate is 5%. A 10% relative improvement (5% → 5.5%) would mean millions in revenue. A 0.1% improvement (5% → 5.005%) isn't worth the engineering effort to ship. So your MDE might be 2% relative (5% → 5.1%)."
> "The smaller your MDE, the more users you need. It's like trying to hear a whisper (small MDE) vs. a shout (large MDE) — you need a quieter room (more data) to hear the whisper."
>
> Concept 3 — The four knobs:
> "There are 4 things that determine how long your experiment needs to run:
> 1. Effect size (MDE) — smaller effect = need more data
> 2. Baseline variance — noisier metric = need more data
> 3. Significance level (alpha, usually 5%) — stricter = need more data
> 4. Power (usually 80%) — higher power = need more data"
>
> Example walkthrough: "Your app has 100,000 daily users. Your conversion rate is 3% with high variance. You want to detect a 5% relative improvement. At 80% power and 5% significance, you need ~50,000 users per group, so about 1 day of traffic in a 50/50 split. But if you want to detect a 1% relative improvement, you need ~1.2 million users per group — that's 12 days."
>
> Concept 4 — Why this matters in practice:
> "If your experiment is underpowered, you'll often conclude 'no effect' even when the feature is actually better. This leads to killing good features."
> Example: "A startup with 10,000 users tests a new onboarding flow. The new flow is actually 8% better. But with only 10,000 users split 50/50, the experiment doesn't have enough power to detect an 8% improvement. Result: 'inconclusive.' They kill the feature. They just lost an 8% improvement because they didn't have enough users."
>
> Concept 5 — CUPED (variance reduction):
> "There's a trick to make your experiments more powerful WITHOUT needing more users. It's called CUPED — using pre-experiment data to reduce noise."
> Analogy: "Imagine you're weighing people before and after a diet. Instead of just measuring their final weight (noisy — people have very different starting weights), you measure the CHANGE in weight. The change has much less variance than the absolute weight. CUPED does something similar — it uses each user's pre-experiment behavior to reduce noise in the experiment."
> "Companies like Microsoft and Netflix use CUPED to detect smaller effects with the same sample size. It's like upgrading your metal detector for free."
>
> End with practical advice: "Always calculate sample size BEFORE running the experiment. If you don't have enough users to detect a meaningful effect, don't run the experiment — you'll just waste time and conclude 'inconclusive.'"
>
> Keep it very slow, repeat each concept with multiple analogies. Target 20 minutes.

**Listen during:** Week 5

---

## Episode 11: Product Sense for Data Scientists — Thinking Beyond the Numbers

**Prompt:**

> Create a podcast episode about developing product sense as a data scientist. The listener is a BIE who is great at SQL and dashboards but needs to develop the skill of connecting data to product decisions. Use lots of examples. Go slow.
>
> Start with the mindset shift: "As a BIE, someone asks you a question and you answer it with data. As a Product DS, you ask the questions yourself. You don't wait for the PM to say 'why did this metric drop?' — you notice it dropped, investigate, and bring the answer AND a recommendation before anyone asks."
>
> Explain Emma Ding's 7 types of product case questions with examples:
>
> Type 1 — Measure Success:
> Question: "How would you measure success for Instagram Reels?"
> Walk through thinking: "First, what's Reels trying to achieve? It's competing with TikTok for short-form video attention. Success means: users are watching Reels (engagement), users are coming back to watch more (retention), and creators are making Reels (supply). My North Star: 'Daily Reels viewers who watch 3+ Reels per session.' Why? Because casual viewers who watch 1 Reel aren't really engaged — they might have just scrolled past one. 3+ means they're actively choosing to consume Reels content."
>
> Type 2 — Diagnose a Metric Change:
> Question: "Uber ride completions dropped 8% this week."
> Walk through: "Segment by city. Oh — it's only in 3 cities. Check weather data. All 3 cities had major snowstorms. Mystery solved. But wait — should rides drop 8% in a snowstorm? Maybe our bad-weather pricing or ETAs are driving users to competitors. There might be an opportunity here..."
> "See how a good DS doesn't just diagnose — they find the opportunity."
>
> Type 3 — Launch Decision:
> Question: "We tested a new checkout flow. Conversion is up 2% but average order value is down 4%. Should we launch?"
> Walk through: "2% more orders but each order is 4% smaller. Net revenue impact: roughly -2%. But wait — are the new converters first-time buyers? If so, their lifetime value might make up for the smaller first order. I'd look at: who are these new converters? What's their predicted LTV? If they're high-LTV users who were previously abandoning cart, the -4% AOV might be worth it long-term."
>
> Type 4 — Improve a Product:
> Question: "How would you use data to improve Spotify's Discover Weekly?"
> Walk through: "I'd look at: (1) What % of Discover Weekly songs get played past 30 seconds? (2) What % get saved to a playlist? (3) What % lead to the user exploring that artist further? Then I'd segment: which users get good recommendations and which get bad ones? What's different about them? Maybe new users with little listening history get worse recommendations — that's an opportunity to improve the cold-start problem."
>
> Type 5 — Design an Experiment:
> Question: "How would you test whether showing delivery time estimates increases order completion on a food delivery app?"
> Walk through the full experiment design in 60 seconds (this is interview pace).
>
> Type 6 — Conflicting Metrics:
> Question: "Notification open rates went up but app uninstalls also went up. What's happening?"
> Walk through: "We're probably sending too many notifications. The people who open them are engaged, but we're annoying the people who don't want them — and they're uninstalling. Solution: segment users by notification preference and reduce frequency for low-engagement users."
>
> Type 7 — Choose Between Options:
> Question: "We can either improve search or improve recommendations. Which should we invest in?"
> Walk through: "I'd look at: where are users dropping off? If 60% of sessions start with search and search has a 30% failure rate, that's a huge opportunity. If recommendations drive 40% of purchases but only 10% of sessions, improving recommendations has high leverage per session but lower reach. I'd estimate the revenue impact of a 10% improvement in each and compare."
>
> End with: "Product sense isn't magic — it's a learnable skill. The key is: always ask 'so what?' after every analysis. The data says X. So what should we DO about it?"
>
> Keep it slow, example-heavy, practical. Target 22 minutes.

**Listen during:** Week 6


---

## Episode 12: Experiment Design Masterclass — End to End

**Prompt:**

> Create a podcast episode that walks through designing an A/B test from start to finish, as if explaining it in an interview. Use a single concrete example throughout so the listener can follow the entire journey. Go slow, explain every decision.
>
> The scenario: "You're the data scientist for DoorDash. The PM wants to test showing a 'Most Popular' badge on the top 3 restaurants in each cuisine category. The hypothesis is that this social proof will help users decide faster and increase order completion."
>
> Walk through every step in detail:
>
> Step 1 — Define the hypothesis:
> "Our hypothesis: Showing a 'Most Popular' badge will reduce decision time and increase order completion rate, because users experience choice overload and social proof helps them decide."
> "Notice I stated the mechanism (WHY we think it'll work), not just the prediction. This matters because if the experiment fails, the mechanism tells us what to investigate."
>
> Step 2 — Choose metrics:
> "Primary metric (OEC): Order completion rate — percentage of sessions that result in a completed order."
> "Why this and not revenue? Because the badge helps users DECIDE, not spend more. If they decide faster, they complete more orders. Revenue per order shouldn't change."
> "Secondary metrics: Time from app open to order placed (should decrease), restaurant detail page views per session (should decrease — less browsing means faster decisions)."
> "Guardrail metrics: (1) Average order value — shouldn't drop (we don't want people choosing cheaper restaurants just because they're popular), (2) Restaurant diversity — we don't want ALL orders going to 3 restaurants and starving others, (3) Customer satisfaction score — shouldn't drop."
> Walk through WHY each guardrail matters with a concrete scenario of what could go wrong.
>
> Step 3 — Randomization unit:
> "We randomize at the USER level. Each user either always sees badges or never sees badges."
> "Why not session-level? Because if a user sees badges in one session and not another, it's confusing and could affect their behavior in the no-badge session."
> "Why not restaurant-level? Because then we can't compare — every user would see some restaurants with badges and some without."
> "Could there be interference? If User A sees the badge and orders from Restaurant X, does that affect User B? Slightly — Restaurant X might get busier and have longer delivery times. But this effect is small enough that user-level randomization is fine."
>
> Step 4 — Sample size and duration:
> "Our baseline order completion rate is 35%. We want to detect a 3% relative improvement (35% → 36.05%). At 80% power and 5% significance, we need about 80,000 users per group."
> "DoorDash has ~1 million daily active users. In a 50/50 split, we get 500,000 per group per day. So we have enough power in 1 day. But we'll run for 2 full weeks. Why?"
> "Reason 1: Day-of-week effects. Ordering patterns differ on weekdays vs. weekends. We need at least 1 full week."
> "Reason 2: Novelty effect. Users might click the badge out of curiosity in week 1 but stop caring in week 2. We need to see if the effect persists."
> "Reason 3: Delivery time effects. If popular restaurants get overwhelmed, delivery times might increase in week 2, which could hurt the metric."
>
> Step 5 — Ramp plan:
> "Day 1-2: 5% of users in treatment. Monitor for crashes, errors, guardrail violations."
> "Day 3: If no issues, ramp to 50%."
> "Day 3-16: Run at 50/50 for 2 full weeks."
>
> Step 6 — Monitoring during the experiment:
> "Daily checks: Are guardrail metrics stable? Any technical errors? Is the split still balanced?"
> "I do NOT check the primary metric daily. Why? Peeking inflates false positive rates. I committed to analyzing after 2 weeks, and I'll stick to that."
>
> Step 7 — Analysis:
> "After 2 weeks, I analyze:
> - Primary metric: Order completion rate is +2.8% (p = 0.01). Statistically significant.
> - Time to order: Decreased by 45 seconds on average. Good.
> - Guardrail 1 (AOV): No change. Good.
> - Guardrail 2 (Restaurant diversity): Top 3 restaurants now get 15% more orders, others get 3% fewer. Hmm — worth monitoring but not alarming yet.
> - Guardrail 3 (Satisfaction): No change. Good.
> - Week 1 vs. Week 2: Effect is +3.2% in week 1 and +2.4% in week 2. Slight novelty effect but still positive in week 2."
>
> Step 8 — Decision:
> "My recommendation: Ship, but with a follow-up plan. The +2.8% completion rate is meaningful (translates to ~$X million annually). Guardrails are clean. The slight novelty decay is normal. However, I'd recommend monitoring restaurant diversity monthly and considering rotating the 'Most Popular' badge to prevent permanent winner-take-all dynamics."
>
> End with: "In an interview, you won't have 18 minutes. But the STRUCTURE is the same. Practice compressing this into 5-7 minutes while hitting every step."
>
> Keep it detailed, slow, one example throughout. Target 22 minutes.

**Listen during:** Week 6-7

---

## Episode 13: Bayesian vs. Frequentist — The Practical Difference

**Prompt:**

> Create a podcast episode explaining the difference between Bayesian and frequentist approaches to statistics and experimentation. The listener is a practitioner who uses p-values at work but has heard "Bayesian" thrown around and wants to understand when each approach is useful. Use lots of analogies and examples. No math formulas. Go slow.
>
> Start with an analogy that captures the core difference:
> "Imagine you hear a noise outside at 3am. The frequentist asks: 'If there were nothing outside, how likely is it I'd hear this noise?' The Bayesian asks: 'Given that I heard this noise, AND given that I live in a safe neighborhood where break-ins are rare, what's the probability someone is actually outside?' The Bayesian uses prior knowledge. The frequentist doesn't."
>
> Explain frequentist approach with an example:
> "You run an A/B test. The frequentist approach says: 'Assume the new feature has NO effect (null hypothesis). Given that assumption, what's the probability of seeing data this extreme? If that probability (p-value) is less than 5%, we reject the null and say the feature works.'"
> "The weird thing: the p-value does NOT tell you the probability that the feature works. It tells you the probability of the DATA given that the feature DOESN'T work. These are different things."
> Example: "p = 0.03 does NOT mean 'there's a 97% chance the feature is better.' It means 'if the feature had no effect, there's only a 3% chance we'd see results this extreme by random chance.'"
> "This is confusing. And it's why many people misinterpret p-values."
>
> Explain Bayesian approach with the same example:
> "The Bayesian approach says: 'I have a prior belief about whether this feature works. Maybe based on past experiments, I think there's a 30% chance it'll improve the metric. Now I run the experiment and update my belief based on the data. After seeing the data, my updated belief (posterior) is that there's an 85% chance the feature improves the metric.'"
> "The Bayesian gives you what you actually WANT: the probability that the feature works."
>
> Confidence interval vs. Credible interval:
> "Frequentist 95% confidence interval: 'If I repeated this experiment 100 times, 95 of those intervals would contain the true effect.' It does NOT mean 'there's a 95% chance the true effect is in this interval.'"
> "Bayesian 95% credible interval: 'There's a 95% probability the true effect is in this interval.' This IS what you intuitively want."
> "See the difference? The Bayesian interpretation is more natural and useful for decision-making."
>
> When to use each — practical guidance:
>
> Use frequentist when:
> - You have large sample sizes (most A/B tests at big tech companies)
> - You want a simple, well-understood framework
> - Your organization's experimentation platform uses it (most do)
> - You don't have strong prior information
> Example: "Standard A/B test at Amazon with millions of users. Frequentist is fine. You have enough data that priors don't matter much."
>
> Use Bayesian when:
> - Small sample sizes (startup, niche feature, B2B product)
> - You want to make decisions DURING the experiment (early stopping)
> - You have strong prior information from past experiments
> - You need to communicate probability of success to stakeholders
> Example: "You're testing a feature for enterprise customers. You only have 200 companies. A frequentist test would take 6 months to reach significance. A Bayesian approach lets you incorporate prior knowledge and make a decision sooner."
> Example: "Netflix uses Bayesian methods because they want to stop experiments early when results are clear — they don't want to show a bad experience to users longer than necessary."
>
> The practical takeaway:
> "For most Product DS interviews, you'll discuss frequentist methods (p-values, confidence intervals, power). But showing you understand Bayesian thinking demonstrates sophistication. The key insight: 'I know when frequentist methods are sufficient and when Bayesian methods add value.'"
>
> End with: "In an interview, if asked 'Bayesian vs. frequentist?', say: 'For standard large-scale A/B tests, frequentist is fine and well-understood. I'd reach for Bayesian when I have small samples, need early stopping rules, or want to incorporate prior experimental knowledge. The choice depends on the context, not a philosophical preference.'"
>
> Keep it slow, analogy-heavy, practical. Repeat the core difference multiple times with different examples. Target 18 minutes.

**Listen during:** Week 7

---

## Episode 14: The BIE to Product DS Transition — Bridging the Gap

**Prompt:**

> Create a podcast episode specifically for someone transitioning from a Business Intelligence Engineer role at Amazon to a Product Data Scientist role at FAANG companies. This is a motivational AND practical episode. The listener should feel "I can do this" by the end. Use lots of concrete examples of how BIE work translates to DS work. Go slow.
>
> Start with validation: "If you're a BIE thinking about becoming a Product DS, you're closer than you think. Seriously. About 70% of what a Product DS does, you already do. The gap is narrower than it feels."
>
> Walk through what's the SAME:
>
> "SQL — You write complex SQL every day. Product DS interviews test SQL. You're already ahead of most candidates who come from academic backgrounds."
> Example: "That query you wrote last week with window functions to calculate rolling 7-day retention? That's literally a DS interview question."
>
> "Understanding business context — You know how Amazon's business works. You know what metrics matter. You know who the stakeholders are. Many DS candidates from academia have never worked with a PM or understood a P&L."
> Example: "When you built that dashboard showing conversion funnel drop-offs by device type? A Product DS does exactly that — but then goes one step further and says 'here's what we should DO about it.'"
>
> "Data pipelines and instrumentation — You know where data comes from, how it can break, and why numbers might be wrong. This is invaluable. Many DS candidates trust data blindly."
> Example: "Remember when you found that the tracking pixel was double-counting mobile sessions? That's Twyman's Law in action. You already have the skepticism that makes a good DS."
>
> "Stakeholder communication — You present to PMs, directors, VPs. You translate data into business language. This is a core DS skill."
>
> Now walk through what's DIFFERENT (the gaps to close):
>
> Gap 1 — Statistical depth:
> "As a BIE, you might calculate a conversion rate and say 'it went up 5%.' As a DS, you need to say 'it went up 5% with a 95% confidence interval of [3.2%, 6.8%], which is statistically significant with p < 0.01, and the effect size is large enough to be practically meaningful.'"
> "The gap: hypothesis testing, confidence intervals, power analysis, experimental design. These are learnable in 4-6 weeks of focused study."
> Example of how to close it: "Your experimentation book covers all of this. Chapters 1-7 will get you 80% of the way there."
>
> Gap 2 — Proactive product influence:
> "As a BIE, you answer questions. As a DS, you ask them. You don't wait for the PM to say 'investigate this.' You notice something in the data, investigate it yourself, and bring a recommendation."
> Example: "Instead of 'here's the dashboard you asked for,' it's 'I noticed retention dropped 8% for users who signed up via paid ads. I investigated and found their onboarding completion rate is 40% lower. I recommend we build a simplified onboarding for paid-acquisition users. Here's the expected impact and how I'd test it.'"
> "The gap: shifting from reactive to proactive. Practice this by looking at your current dashboards and asking 'what would I recommend based on this data?'"
>
> Gap 3 — Python for analysis:
> "BIEs typically work in SQL + visualization tools. DSs add Python (pandas, scipy, statsmodels) for statistical analysis, modeling, and automation."
> "The gap: not huge. You don't need to be a software engineer. You need to be comfortable doing data manipulation and statistical tests in Python."
> Example: "Can you load a CSV, compute a t-test, and plot the results in Python? That's the bar. Not building ML models from scratch."
>
> Gap 4 — Causal thinking:
> "BIEs report what happened. DSs figure out WHY it happened and whether one thing CAUSED another."
> Example: "BIE says: 'Users who use feature X have 20% higher retention.' DS asks: 'Does feature X CAUSE higher retention, or do already-engaged users just happen to use feature X?' Then designs an experiment or causal analysis to find out."
>
> End with a realistic timeline and motivation:
> "If you study 45-60 minutes a day for 12 weeks, you can close these gaps. You're not starting from zero — you're starting from 70%. The BIE-to-DS transition is one of the most natural career moves in tech. People do it all the time at Amazon. You already have the hardest parts: business context, SQL mastery, and stakeholder skills. The rest is learnable."
>
> Keep it motivational, practical, example-heavy. The listener should feel energized, not overwhelmed. Target 18-20 minutes.

**Listen during:** Week 1 (START HERE — listen first for motivation)

---

## Suggested Listening Schedule

| Week | Episode(s) | Topic | Best For |
|------|-----------|-------|----------|
| 1 | #14, #1 | BIE→DS transition (motivation), A/B testing basics | Morning walks |
| 2 | #2, #3 | OEC, Experiment pitfalls | Commute |
| 3 | #4, #5 | Product metrics, Metric diagnosis | Walks |
| 4 | #6, #7 | Behavioral mastery, Causal inference | Commute |
| 5 | #10, #8 | Statistical power, Meta interview | Walks |
| 6 | #9, #11 | Amazon interview, Product sense | Commute |
| 7 | #12, #13 | Experiment design, Bayesian vs. Frequentist | Walks |
| 8-12 | Re-listen to weakest areas | Reinforcement | Anytime |

---

## Tips for Getting the Best Podcast Output from Gemini
- Paste the prompt directly into Gemini's NotebookLM or audio generation feature
- If the output is too short, add: "Make this a detailed, in-depth episode of at least 20 minutes with many examples"
- If too academic, add: "The listener learns best through stories and analogies, not definitions. Use at least 5 concrete product examples."
- If too fast, add: "Go slow. Repeat key concepts. Pause between sections. The listener is absorbing this while walking."
- You can also paste relevant sections from your prep notes as "source material" for Gemini to reference
