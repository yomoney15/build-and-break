---
name: plan
description: Plan carefully before executing a task. Use whenever the user says "/plan" or wants to think through something before starting — games, projects, code, business initiatives, anything complex. Claude conducts an adaptive interactive interview using multiple-choice questions (branching based on task type and previous answers), generates a comprehensive markdown plan with phases, decisions, risks, and timeline, then offers to collapse it into one step-by-step prompt for immediate execution.
---

# Plan

A skill for thinking through complex tasks before executing them. Type `/plan [task description]` and Claude will guide you through a structured, adaptive planning process using interactive questions.

## How It Works

### Phase 1: Adaptive Interactive Interview

Claude uses `ask_user_input_v0` to ask **1-3 multiple-choice questions per round**, with:
- **Short header** (≤12 characters, e.g., "Vision", "Timeline", "Team size")
- **One-sentence question**
- **2-3 options** with descriptions of each tradeoff
- **Recommended option listed first**
- **Free-text "Other" always included** for custom answers

**Questions branch based on:**
- **Task type** — Game? Business? Code? Different questions for each
- **Your answers** — Follow-ups are tailored to what you said
- **Complexity** — Simple tasks get 5-7 questions; complex tasks ask more

**Example flow:**
1. Round 1: "What's your core vision?" → You pick "Idle game"
2. Round 2 (adaptive): Based on idle, ask about monetization, retention hooks, audience
3. Round 3 (adaptive): Based on idle + 1-2 week timeline, ask about prestige mechanics, leaderboards, offline progression

No pre-built decision tree. The model reads your answers and decides what to ask next.

### Phase 2: Markdown Plan Generated

Claude synthesizes your interview answers into a **markdown file** with:

1. **Overview** — One-paragraph summary of what you're building
2. **Development Phases** — Sequenced, actionable steps with:
   - Realistic effort estimates (hours, days, weeks)
   - Concrete deliverables per phase
   - Testing checklists
3. **Key Decisions** — Table of things you should decide *now* (not during execution):
   - Decision name
   - Options considered
   - Your choice
   - Rationale
4. **Risks & Mitigations** — Plausible risks for your specific project paired with concrete mitigations
5. **Timeline** — Day-by-day or week-by-week breakdown
6. **Success Metrics** — How you'll measure if launch was successful (DAU, conversion, retention, engagement)
7. **Implementation Notes** — Technical guidance, data structures, testing strategy

The plan is **specific to your project**, not generic templates.

### Phase 3: Approval & One-Prompt Implementation

The markdown plan is shown to you. Then Claude asks:

**"Ready to implement this as one consolidated prompt?"**

Two choices:
- **Yes** → Claude collapses the entire plan into a single step-by-step **execution prompt** with checklists you can follow immediately
- **No** → Stay in plan mode and refine sections (ask Claude to rewrite a phase, adjust timelines, etc.)

If you choose "No," Claude asks what to change and regenerates the full plan.

---

## When to Use This Skill

- You're starting something complex and want to think before doing
- You're not sure of the best sequence or approach
- You need to identify risks, blockers, or dependencies upfront
- You want a documented plan to reference during execution
- You're coordinating with others and need a shared reference
- You have multiple options and want clarity on tradeoffs

---

## Skill Behavior

- **Interactive, not text-only** — Questions appear as clickable options you select from
- **Adaptive, not generic** — Questions change based on task type and your answers
- **Specific, not templated** — Plans are tailored to your project, not cookie-cutter
- **Executable, not aspirational** — Phases have effort estimates, deliverables, and testing checklists
- **Live and refinable** — Refine the plan before implementing, or implement immediately

---

## Example Workflow

**You type:** `/plan a Roblox idle fishing game for 1-2 weeks solo with AI assistance`

**Round 1 (Claude asks 3 questions):**
1. Core gameplay vision? → You pick "Idle/AFK-friendly"
2. Timeline? → You pick "1-2 weeks"
3. Using AI workflow? → You pick "Yes"

**Round 2 (Claude asks 3 adapted questions):**
1. Monetization focus for idle games? → You pick "Premium currency + cosmetics"
2. What keeps players coming back? → You pick "All three" (loop + prestige + upgrades)
3. Target audience? → You pick "13-18 year olds"

**Round 3 (Claude asks 3 more adapted questions):**
1. Prestige mechanic (multipliers vs. cosmetics)? → You pick "Both"
2. Leaderboards or competitive elements? → You pick "Yes, global leaderboards"
3. Idle progression (auto-fisherman mechanics)? → You pick "Instant catch + auto-fisherman"

**Claude generates a 5-phase markdown plan:**
- Phase 1: Core loop (click → catch → currency → upgrades) — 4 days
- Phase 2: Premium currency & shop — 2 days
- Phase 3: Prestige system — 2 days
- Phase 4: Leaderboards & auto-fisherman — 2 days
- Phase 5: Polish & balance — 2 days
- Plus: Key decisions table, risk mitigations, success metrics

**Claude asks:** "Ready to implement this as one prompt?"
- **Yes** → Gets a step-by-step execution guide
- **No** → Can refine the plan first

---

## Notes for Claude Using This Skill

### Interview Phase
- **Identify task type first.** Game? Business? Code? Infrastructure? Interview questions adapt.
- **Ask 1-3 per round.** Keep rounds short and snappy. Multiple rounds is better than one 10-question form.
- **Branching is dynamic.** Read the user's answers and decide what to ask next. Don't follow a fixed tree.
- **One sentence per question.** Keep questions clear and specific.
- **Recommended option first.** Always put the most sensible option first; mark it "(Recommended)".
- **Include tradeoff descriptions.** Each option should explain what it gives up (time, complexity, cost, features).
- **Free-text "Other" always.** Let users type custom answers if options don't fit.

### Planning Phase
- **Synthesize into narrative.** Don't just repeat answers; weave them into a cohesive plan.
- **Phases are actionable.** Each phase has concrete deliverables and testing steps, not vague goals.
- **Effort estimates matter.** Give hours/days per phase; users need to know if 1-2 weeks is realistic.
- **Decisions table is key.** List the things they should decide *now* so they're not guessing during execution.
- **Risks are specific.** Not "the project might fail"—"players might quit before first prestige if threshold is too high → lower from $100K to $50K."
- **Metrics are measurable.** DAU, conversion rate, retention curves, leaderboard engagement—things you can actually track.
- **Timeline is granular.** Days or weeks depending on scope; users need to know if they're on track.

### Approval Phase
- **Offer one-prompt implementation.** Make it clear that yes → collapsed execution prompt that's immediately actionable.
- **Be ready to refine.** If they say "no," ask what to change and regenerate the full plan.
- **Don't push.** Either option is valid. Some people prefer to keep the plan as reference; others want to execute immediately.

---

## Tips for Best Results

1. **Be specific in your `/plan` request.** "Plan a Roblox game" is vague; "Plan a Roblox idle fishing game for 1-2 weeks, solo, AI-assisted" gives Claude context.
2. **Answer questions honestly.** If you're not sure about timeline, say so; Claude will offer scenarios.
3. **Use the key decisions table during execution.** Refer back to it when tempted to scope-creep or change direction.
4. **Track metrics from Day 1.** If the plan says "prestige rate should be 30%," track it immediately after launch.
5. **Refine the plan, don't ignore it.** Plans are guides, not straitjackets, but they're only useful if you reference them.

---

## Skill Behavior & Guarantees

- **Interview is interactive.** Uses `ask_user_input_v0` for clickable questions, not text-only.
- **Plan is markdown.** Downloadable, shareable, editable in Claude or any text editor.
- **One-prompt option works.** If you say yes, you get a single consolidated prompt that walks through the plan step-by-step with checklists.
- **Refinement always available.** Pick "no" and ask Claude to change anything; it regenerates the full plan.
- **Task-specific, not generic.** A game plan looks different from a business plan; Claude adapts.
