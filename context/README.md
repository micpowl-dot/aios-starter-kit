# Context layers (load in order)

This kit is organized as **context-engineering layers**. A fresh AI session loads them in a
deliberate order so it is grounded before it acts. Lower layers are stable; higher layers change
with the work.

```
00-system   →   01-project   →   02-task
(how I work)    (what this is)    (what to do now)
```

| Layer | Question it answers | Changes how often | Lives in |
|---|---|---|---|
| **00-system** | How do I operate? Voice, frameworks, standing rules. | Rarely (quarterly). | `00-system/`, `CLAUDE.md`, `references/` |
| **01-project** | What is this project, who's involved, what's the goal? | Per project. | `01-project/`, the vault's `01 - Projects` |
| **02-task** | What artifact am I producing right now, and how? | Every request. | `02-task/`, `.claude/skills/` |

**Why order matters.** The system layer is the brain rewire (the Three Ms, the voice rules). The
project layer is the WHAT. The task layer is the HOW for a single request. Skip a layer and the AI
guesses; load them in order and it acts like it already works here.

**The load order is documented in `CLAUDE.md`**, which the agent reads first. `/onboard` fills
00-system and 01-project; `/level-up` adds to 02-task as you build new capabilities.

The Four Cs map onto these layers: **Context** = layers 00 + 01, **Connections** + **Capabilities** =
layer 02 (reaching tools and shipping artifacts), **Cadence** = the integrations that run the task
layer without you asking.
