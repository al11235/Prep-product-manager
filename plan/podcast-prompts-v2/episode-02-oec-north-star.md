# Episode 2: The OEC — Choosing Your One Metric That Matters

## Instructions for Gemini

Create a conversational podcast episode (two hosts discussing) based on the detailed source material below. Make it engaging, story-driven, and slow-paced. The listener is a data professional who runs dashboards with many metrics but hasn't thought deeply about which ONE metric should determine if an experiment succeeded or failed.

Target: 40 minutes. Use ALL the material below — don't summarize, expand on it with conversation.

---

## SOURCE MATERIAL (use this as the basis for the episode):

### The Problem: Too Many Metrics, No Clear Answer

**The scenario every DS faces:** You run an A/B test. Results come back:
- Click-through rate: +5% ✅
- Time on page: -3% ❌
- Revenue per user: +1% (not significant) 🤷
- Page load time: +200ms ❌
- Customer support tickets: no change

Did the experiment succeed or fail? If you have 5 metrics and some go up and some go down, how do you decide?

**What happens without an OEC:** The PM cherry-picks whichever metric supports their pre-existing opinion. "Look, CTR went up!" The engineer says "But load time got worse!" The VP says "Revenue didn't move, so it doesn't matter." Everyone argues. No decision gets made. Or worse — a decision gets made based on the loudest voice in the room, not data.

**The solution:** Before the experiment starts, declare ONE primary metric that determines success or failure. This is your OEC — Overall Evaluation Criterion. One number. Ship if it goes up. Kill if it doesn't. Everything else is secondary information.

---

### What Makes a Good OEC?

**Five criteria (a good OEC must pass all five):**

1. **Moves when users get more value.** If users are happier/more successful, the OEC should go up. If users are frustrated, the OEC should go down.

2. **Hard to game.** If a team can make the OEC go up by doing something that hurts users (like sending more spam notifications to boost "engagement"), it's a bad OEC.

3. **Measurable in the experiment timeframe.** If your true goal is "5-year customer lifetime value," you can't measure that in a 2-week experiment. You need a proxy that moves in 2 weeks and correlates with long-term value.

4. **Sensitive enough to detect changes.** Some metrics are too noisy or too stable to move in an experiment. Revenue might not move from a UI change, but clicks will.

5. **Aligned with long-term business health.** The OEC should predict long-term outcomes, not just short-term wins.

---

### Example 1: Search Engine (Google)

**Bad OEC: "Number of searches per user per day"**

Why it's bad: Think about what happens when search is TERRIBLE. Users search, don't find what they want, and search AGAIN. And again. More searches could mean WORSE quality. This metric goes UP when the product gets WORSE.

A team could "improve" this metric by making search results deliberately bad — users would keep searching. Obviously terrible, but the metric would celebrate.

**Better OEC: "Successful search sessions"**

Definition: A session where the user searches, clicks a result, and does NOT return to the search page within 30 seconds. This means they found what they needed.

Why it's better: It goes up when users find what they want (value delivered). It goes down when search quality degrades. It's hard to game. It's measurable in real-time.

**Even better (what Google actually uses):** They combine several signals into a composite metric — but the core logic is the same: measure whether users accomplished their goal, not whether they kept searching.

**The counterintuitive insight:** The best OEC for a search engine is one that makes users LEAVE (because they found what they needed). Less usage = better product. This confuses many people.

---

### Example 2: Netflix

**Bad OEC: "Total hours watched"**

Why it's problematic: A user might binge-watch 8 hours of mediocre content because the autoplay feature keeps the TV on while they're half-asleep. Hours go up. But the user isn't getting value — they'll eventually feel "Netflix is a waste of time" and cancel.

Also gameable: Netflix could recommend increasingly addictive/sensationalist content to maximize hours. Short-term hours up, long-term brand quality down.

**Better OEC: "Percentage of users who watch something they subsequently rate 4+ stars within their first 7 days"**

Why it's better: Captures QUALITY of the experience, not just quantity. A user who watches 2 hours of something they love is more valuable than a user who watches 8 hours of something mediocre.

**What Netflix actually cares about:** Retention (do people keep subscribing). But retention takes months to measure. So they use proxy OECs in experiments that correlate with retention: engagement with high-quality content, completion rates of series, re-engagement after periods of inactivity.

**The tension: short-term vs. long-term**
- Short-term: Hours watched is easy to move. Autoplay, notifications, cliffhangers.
- Long-term: User satisfaction and retention. Harder to move but more valuable.
- A good OEC balances both: "engagement with content the user subsequently values."

---

### Example 3: Uber (Two-Sided Marketplace)

**The challenge:** Uber has TWO customers — riders AND drivers. An OEC that's great for riders might be terrible for drivers (and vice versa).

**Bad OEC: "Rides requested"**
- Only measures demand. Ignores whether rides actually happen. Ignores driver experience.

**Bad OEC: "Driver hours online"**
- Only measures supply. Ignores rider experience. A driver stuck without rides for hours counts as "good" by this metric.

**Better OEC: "Rides completed per active hour"**
- Captures BOTH sides: a ride is completed only if a rider got picked up AND a driver completed the trip. Per active hour normalizes for marketplace size.
- Goes up when matching improves, prices are fair, wait times are low.
- Goes down when drivers can't find riders or riders can't find drivers.

**Even better (marketplace health):** "Gross bookings per active rider AND driver satisfaction score above threshold"
- This is a composite: the marketplace is healthy only when BOTH sides are satisfied.

**The key insight for marketplaces:** Your OEC must capture value for BOTH sides. If you optimize only for one side, the other side leaves, and the marketplace collapses.

---

### Example 4: Amazon (E-Commerce)

**Bad OEC: "Total revenue"**
- Can go up by raising prices (hurts customers) or by tricking people into buying things they don't want (short-term win, long-term trust destruction).

**Better OEC: "Purchase frequency" (orders per active customer per month)**
- Goes up when customers find what they want, trust the platform, and come back.
- Goes down when experience is bad (slow delivery, wrong items, confusing UX).
- Hard to game without genuinely improving the experience.
- Measurable in experiment timeframes (2-4 weeks).

**What Amazon reportedly uses (per Jeff Bezos philosophy):** A combination of selection, price, and convenience. Their internal metrics are proxies for "did the customer get what they wanted, at a good price, quickly?"

---

### Guardrail Metrics — The Safety Net

**What they are:** Metrics that you don't TRY to improve, but that must NOT get worse. They're your "do no harm" constraints.

**The road trip analogy:**
- Your OEC is your destination (where you're trying to go)
- Guardrail metrics are the speed limit and fuel gauge — you don't optimize for them, but if you violate them, you pull over and stop

**Why you need them:** A clever team could improve ANY single OEC by sacrificing something else:
- Improve CTR by making buttons misleading → user trust drops
- Improve engagement by sending more notifications → users get annoyed and uninstall
- Improve conversion by hiding the price until checkout → customer support tickets spike

Guardrails catch these trade-offs.

**Examples of common guardrails:**

| OEC | Guardrail (must not degrade) |
|-----|------------------------------|
| Click-through rate | Revenue per user, page load time |
| Engagement time | User satisfaction (NPS), uninstall rate |
| Conversion rate | Average order value, return rate |
| Messages sent | Spam reports, block rate |
| Watch time | Subscription cancellation rate |

**How to use guardrails in practice:**
1. Before the experiment: define your OEC AND 2-3 guardrails
2. During the experiment: monitor guardrails daily (this is the one thing you CAN peek at)
3. After the experiment: only ship if OEC improved AND all guardrails are clean
4. If OEC improved but a guardrail degraded: investigate. Usually means you need to iterate, not ship.

**Real-world example:** A team tests a more aggressive notification strategy.
- OEC (daily active users): +4% ✅
- Guardrail (uninstall rate): +15% ❌
- Decision: Do NOT ship. The notifications are bringing people back but also driving people away permanently. The long-term cost of losing users to uninstalls outweighs the short-term DAU gain.

---

### Composite OECs — When One Metric Isn't Enough

**Sometimes you need to COMBINE metrics into a single score.**

**Example:** Microsoft's Bing search OEC combines:
- Sessions per user (engagement)
- Distinct queries (breadth of usage)
- Clicks on results (finding what they need)
- Absence of "re-searches" (finding it on the first try)

They weight these into one number. This prevents gaming any single dimension.

**How to build a composite:**
1. Identify 3-4 metrics that together capture "user value"
2. Normalize them to the same scale
3. Weight them (usually based on correlation with long-term outcomes like retention)
4. Sum into one score

**The trade-off:** Composite OECs are harder to interpret ("the composite went up 2% — which component drove it?") but harder to game and more representative of true value.

---

### How to Choose an OEC — The Practical Framework

When asked "What metric would you use as your OEC?" in an interview, walk through these questions:

1. **"What's the user goal?"** — What is the user trying to accomplish? The OEC should reflect whether they accomplished it.

2. **"Can this be gamed?"** — If a team could improve this metric by doing something users would hate, it's a bad OEC. Pick something harder to game.

3. **"Can I measure it in 2 weeks?"** — If not, what's a proxy that correlates with the long-term goal? (Activation rate as a proxy for retention. Session quality as a proxy for lifetime value.)

4. **"Does it capture both sides?"** — For platforms/marketplaces: does this metric reflect value for ALL stakeholder groups, not just one?

5. **"What are my guardrails?"** — What important things could get WORSE if I optimize this OEC?

**Interview line:** "My OEC would be [X] because it captures whether users are getting value, it's hard to game, and it's measurable in our experiment timeframe. My guardrails would be [Y] and [Z] to ensure we don't sacrifice long-term health for short-term gains."

---

### Common Interview Questions About OEC

**Q: "How would you measure success for [feature]?"**
→ This is asking for your OEC + supporting metrics + guardrails.

**Q: "Two experiments have conflicting results — one improved OEC A, the other improved OEC B. How do you decide?"**
→ Ask: which OEC better predicts long-term business health? That one wins.

**Q: "The PM wants to use 'revenue' as the OEC. What do you think?"**
→ Revenue is often a bad OEC: too slow to move in short experiments, can be gamed (raise prices), and doesn't capture user value directly. Better to use a proxy that PREDICTS revenue (like purchase frequency or conversion rate).

**Q: "Can you have multiple OECs?"**
→ No. The whole point is ONE metric that decides ship/kill. You can have multiple SECONDARY metrics and GUARDRAILS, but only one OEC. If you have two OECs and they disagree, you haven't actually solved the decision problem.

---

## PODCAST STYLE INSTRUCTIONS:

- Two hosts discussing: one explains (the "teacher"), one asks questions like "But what about...?" and "Wait, wouldn't that mean...?"
- Start with the problem: "You have 5 metrics, some up, some down — how do you decide?"
- Build through the examples: search engine → Netflix → Uber → Amazon (increasing complexity)
- For each example: present the BAD OEC first, explain why it fails, then present the BETTER OEC
- Spend significant time on guardrails — use the notification example (DAU up but uninstalls up)
- The learner host should push back: "Why can't we just use revenue?" "Why only ONE metric?"
- Pace: SLOW. Each example should breathe. Don't rush through them.
- End with: "The OEC is your single source of truth for ship/kill decisions. Pick it before the experiment. Make sure it captures user value, is hard to game, and is measurable in your timeframe. Then add guardrails to protect what could break."
