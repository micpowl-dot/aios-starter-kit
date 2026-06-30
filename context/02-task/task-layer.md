# Layer 02 — Task (turning a request into an artifact)

The top layer. It answers: for THIS request, what am I producing and how? This is where the Four Cs'
**Capabilities** live: a short phrase triggers a multi-step job that ships a real artifact.

## How the task layer works
1. A request arrives ("draft the weekly update", "build the launch checklist").
2. The agent already holds layer 00 (how you work) and layer 01 (the project). It does not re-ask.
3. It runs the matching **skill** in `.claude/skills/`, or follows a saved pattern in `references/sops/`.
4. The output lands as an artifact (a doc, a message draft, a rendered file), and any decision is
   logged to `decisions/log.md`.

## The skills that ship
| Skill | What it does |
|---|---|
| `/onboard` | One-time setup interview. Fills layers 00 and 01. |
| `/audit` | Weekly read-only Four Cs gap report. Tells you the next gap to close. |
| `/level-up` | Weekly Three Ms interview. Surfaces and scopes ONE automation to build. |

## Growing the task layer
Every `/level-up` run can add a new capability here: a new skill, a saved SOP, or a sub-agent. The
rule from `EXPANSIONS.md` applies, add it when you'll use it 3+ times, not before. Don't automate a
task (Cadence) until it works by hand here first.
