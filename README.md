# build-and-break

Two Claude skills for going from idea to informed decision: plan it, then try to break it.

## Skills

### `/plan`
Plans carefully before executing a task. Runs an adaptive, interactive interview (1-3 multiple-choice questions per round, branching on task type and your answers), then synthesizes the answers into a markdown plan covering phases, key decisions, risks, timeline, and success metrics. Offers to collapse the plan into a single step-by-step execution prompt.

See [`plan/SKILL.md`](plan/SKILL.md).

### `/grill-me`
Criticizes your work and ideas before you commit time and resources to them. Asks a few targeted clarifying questions, then delivers a blunt, structured evaluation across market viability, technical feasibility, business model, competitive landscape, execution risk, and opportunity cost — ending in a clear "worth pursuing," "needs rework," or "not worth it."

See [`grill-me/SKILL.md`](grill-me/SKILL.md).

## Usage

Each skill lives in its own folder with a `SKILL.md` that Claude reads to learn when and how to use it. Add either folder to your Claude skills directory to enable the corresponding slash command.

## Suggested workflow

1. `/plan` — turn a rough idea into a structured, phased plan.
2. `/grill-me` — stress-test that plan (or any idea) before you invest in it.
3. Revise the plan based on what survives scrutiny, then execute.
