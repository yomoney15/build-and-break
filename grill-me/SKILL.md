---
name: grill-me
description: Criticize your work and ideas to see if they're worth pursuing. Use when you want harsh but fair evaluation of a project, idea, or plan before you commit time and resources. Claude asks clarifying questions, then delivers a critical red flag report across market viability, technical feasibility, business model, timeline, and competitive risk. Ends with a clear yes/no recommendation. Tone is blunt about cons—not roasting, but enough to make you feel the weight of potential downsides.
---

# Grill Me

A skill for stress-testing your ideas before you commit to them. Type `/grill-me` and Claude will ask critical questions, then deliver a harsh but fair evaluation of whether your idea is actually worth pursuing.

## How It Works

### Phase 1: Clarifying Questions

Claude asks **2-3 targeted questions** to understand:
- What you're actually trying to build/do
- Who the audience/market is
- What resources (time, money, team) you have
- What success looks like
- What constraints exist

Questions are specific based on your chat history and the idea you've mentioned.

### Phase 2: Critical Evaluation Report

Claude systematically evaluates across 5-6 dimensions:

1. **Market & Audience** — Is there a real audience? Do they actually want this? Can you reach them?
2. **Technical Feasibility** — Can you actually build it? Are there hidden complexity costs? Is the timeline realistic?
3. **Business Model** — Will it make money? Are monetization assumptions solid? Can you sustain it?
4. **Competitive Landscape** — Are there competitors already doing this? Why would yours win?
5. **Execution Risk** — What's most likely to kill this project? Team gaps? Scope creep? Resource constraints?
6. **Opportunity Cost** — Is this the best use of your time vs. other ideas?

Each dimension has:
- **Assessment:** What's actually true about this idea
- **Red flags:** Specific concerns and weaknesses
- **Assumptions that could break:** Things you're betting on that might be wrong

### Phase 3: Clear Recommendation

Claude delivers a **direct yes/no:**

- **"Worth pursuing"** — Go ahead, but watch these red flags
- **"Needs rework first"** — Not ready; here's what to fix before committing
- **"Not worth it"** — Cons outweigh pros; consider pivoting instead

---

## When to Use This Skill

- **Before you invest heavily** in a project (time, money, team)
- **When you need to hear hard truths,** not cheerleading
- **To pressure-test assumptions** you're relying on
- **To compare ideas** (run grill-me on 2-3 concepts and see which survives scrutiny)
- **When impostor syndrome is lying to you** (and you need to know if it's a real problem or just nerves)
- **Before pitching to a manager/investor** (know the weak points they'll attack)

---

## Skill Behavior

- **Questions are adaptive.** Based on your chat history and what you've already said, Claude asks only the critical clarifications needed.
- **Evaluation is specific, not generic.** Red flags are tied to *your* idea, not boilerplate risks.
- **Tone is harsh but fair.** Not mean or dismissive, but blunt about downsides. You'll feel the weight of the cons.
- **Recommendation is clear.** Yes, no, or "rework first"—no wishy-washy maybes.
- **Report is actionable.** If recommendation is "rework," Claude explains what to fix.

---

## Example Workflow

**You type:** `/grill-me` (in a conversation where you've been discussing your fishing idle game idea)

**Claude asks 2-3 clarifying questions:**
1. "You said 1-2 week MVP with AI assistance. How much time can you actually commit post-launch to updates and live service?"
2. "For 13-18 year olds, what's your plan to get the first 100 users? How are you acquiring audience?"
3. "You mentioned leaderboards. Have you thought about moderation and toxicity from competitive teens?"

**You answer.** Claude synthesizes and delivers:

---

## Critical Evaluation Report: Fishing Idle Game

### Market & Audience
**Assessment:** 13-18 year olds are a proven audience for idle games (clicker heroes, cookie clicker, etc.). The genre works.

**Red flags:**
- Fishing is NOT a trend right now. Anime waifus, battle royales, and survival games are. Fishing is niche.
- Competing against established idle games with years of content. Cookie Clicker has 15 years of players.
- Roblox market is saturated with simulators. What makes *your* fishing game special? Prestige? Leaderboards? Those aren't unique.
- No plan to acquire first 100 users. How are they finding your game?

**Assumptions that could break:**
- "13-18 year olds will play this if I build it." False. They need a reason—discovery, friends, streamers. Do you have any?
- "Prestige system = retention." Prestige works *if* the base loop is addictive. If fishing is boring, prestige just delays the quit.

### Technical Feasibility
**Assessment:** Building a 1-2 week MVP is realistic. Idle mechanics, data storage, leaderboards are all doable in that timeframe.

**Red flags:**
- Leaderboards sound simple but can be surprisingly complex at scale. Cheating detection, real-time updates, fair ranking—you've glossed over these.
- Auto-fisherman offline earnings = potential exploit surface. Players will find ways to game this. You need server-side validation, which adds complexity.
- You're solo + AI-assisted. What happens if you hit a roadblock? No team to ask. AI can help, but debugging is slower.

**Assumptions that could break:**
- "AI will write code perfectly." It won't. You'll spend time debugging and refining. 1-2 weeks might slip to 3 weeks.
- "Roblox DataStore is sufficient." At scale, it can be slow. If your leaderboard bogs down, players leave.

### Business Model
**Assessment:** Premium currency + cosmetics is a proven model for idle games. Prices ($5-10 bundles) are reasonable for this audience.

**Red flags:**
- You have NO monetization history. First game's monetization almost always underperforms because you don't know your audience's willingness to pay.
- 13-18 year olds have less disposable income than adults. Conversion target of 5-10% might be too high. Expect 2-3%.
- Cosmetics are your revenue driver, but you're not differentiating them. "Rod skin" isn't compelling. Why spend Robux on a rod skin instead of skins in Fortnite or Roblox catalog?
- No plan for sustained revenue post-launch. New cosmetics weekly? Who designs them? You? Alone?

**Assumptions that could break:**
- "Prestige cosmetics will drive monetization." Prestige players are already invested; they'll play free. Whales who haven't prestige'd yet have low monetization intent.
- "Players will pay for cosmetics they earned in-game already." Friction = lower conversion. Consider locking cosmetics behind $$.

### Competitive Landscape
**Assessment:** Fishing-themed games exist but aren't dominant. No major competitor owns the "idle fishing" niche on Roblox (yet).

**Red flags:**
- "Yet" is the problem. A AAA studio or established Roblox dev could clone this in 2-3 weeks with better art and faster updates.
- Fishing Tycoon, Fishing Simulator, Fish Idle already exist on Roblox. You're entering crowded waters (pun intended).
- No network effects or lock-in. Players can switch to a better fishing game with one click. Your only moat is: cosmetics library and leaderboard history. Weak.

**Assumptions that could break:**
- "First-mover advantage will protect me." Roblox moves fast. Your 1-2 week MVP will be copied within a month.

### Execution Risk
**Assessment:** Technical execution is manageable. Business execution is the risk.

**Red flags:**
- You're optimizing for launch speed, not quality. A buggy MVP loses players immediately. Testing is underfunded in your timeline.
- Post-launch, you're solo managing live service (cosmetics, leaderboards, balance tweaks). One person + passive income game = burnout or abandonment.
- You're betting on Day 1 retention being high enough to justify continued work. If it's not, do you abandon it or pivot? You haven't decided.

**Assumptions that could break:**
- "I can maintain this solo post-launch." You can, but for how long? 3 months? A year? This isn't a side project; it's a live service game.

### Opportunity Cost
**Assessment:** 1-2 weeks is not a huge time sink. But post-launch is.

**Red flags:**
- You're learning monetization, live service, and Roblox game dev simultaneously. High learning curve = slow iteration.
- If this game underperforms, you've spent 2 weeks on a dead project and 2+ months on live service maintenance that generates $0 net revenue.
- You have other projects (Solid Source Realty AI, other Roblox ideas, learning goals). Is fishing idle game the highest-ROI use of your time?

---

### Recommendation

**"Needs rework first."**

The idea is *buildable*, but not ready to commit to yet. Here's why:

1. **Market risk is real.** Fishing isn't trending. You have no organic discovery plan. Prestige systems are table-stakes in idle games, not differentiators.
2. **Monetization is unproven.** First game's revenue always underperforms. Expect $0-10/month, not $100+. Is that worth your time post-launch?
3. **Competitive moat is weak.** Your game can be cloned in 2 weeks by a studio with better art. What keeps players from switching?
4. **Solo execution risk is high.** You're managing design, code (via AI), balancing, cosmetics, and live service alone. Burnout is likely.

**Before you build, answer these:**
- How are you acquiring the first 1,000 users? (Discovery plan?)
- What's the differentiator vs. existing fishing games? (Why is prestige + leaderboards special?)
- What's your post-launch revenue target and threshold for "this isn't worth it"? (Be realistic: probably $50-200/month)
- Are you committed to 6+ months of live service, or is this a 2-week MVP + abandon experiment?

**If you can answer those convincingly, build it.** If not, consider:
- **Pivot to a different game concept** (battle royale? tycoon simulator?) that has clearer monetization and differentiation
- **Partner with someone** to share live service load
- **Build a 1-week prototype first** and test with real users before committing to full MVP

---

**Your call:** Rework it and re-grill, or try a different idea?
