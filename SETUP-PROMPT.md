# Setup Prompt — paste this into Claude Code

Clone this repo, open the folder in Claude Code, and paste the prompt below as your
first message. It bootstraps the whole kit for you (solo) or your team. It is
read-and-confirm: it will not overwrite anything or send anything without asking.

---

```
You are setting up my AI Operating System (AIOS) from this starter kit. Work through
these phases in order. Confirm with me at each gate. Never overwrite an existing file
without asking, and never send or publish anything on my behalf.

PHASE 0 — Orient (read-only)
- Read README.md, CLAUDE.md, EXPANSIONS.md, and context/README.md (the context layers).
- Read references/3ms-4cs-framework.md so you hold the Three Ms and Four Cs.
- Tell me, in 3 lines, what this kit is and the order we will build the Four Cs.

PHASE 1 — Context (layer 00 + 01)
- Run /onboard. Interview me with the 7 questions in aios-intake.md (one at a time).
  For the voice sample, make me PASTE real writing; do not let me describe it.
- From my answers, fill: context/ (about me/business), references/voice.md, connections.md,
  and CLAUDE.md persona/priorities. Show me each file before saving.
- Decide solo vs team: if team, also scaffold context/01-project/ entries per workstream
  and note who owns what.

PHASE 2 — Source of truth (the vault)
- Confirm where my human-readable notes live. If I use Obsidian, point the vault/ mirror
  at it; if not, the in-repo vault/ IS the source of truth.
- Read vault/AGENTS.md and follow its lane + numbering rules for everything you write.

PHASE 3 — Connections (layer 02 wiring)
- Walk connections.md domain by domain. For each tool I name, tell me the cheapest way to
  reach it (MCP, script, or export) and what to put in .env / references/{tool}-api.md.
- Do NOT enter any credentials yourself. Hand me each credential step to do.

PHASE 4 — Cadence (integrations)
- Read integrations/README.md. Help me wire ONE webhook (integrations/webhooks/) and ONE
  "show your work" dashboard (integrations/dashboard/) using the templates, starting from
  the AI Day worked examples. Do not automate a workflow that does not work manually first.

PHASE 5 — First loop
- Run /audit (read-only Four Cs gap report) and tell me the single highest-leverage gap.
- Then we stop. I will run /level-up on day 14 to ship the first automation.

Rules: plain English, bullets over paragraphs, short sentences, no em dashes. Anything
external-facing (email, post, message) is a draft until I approve it. Log meaningful
decisions to decisions/log.md.
```

---

## After setup

- **Day 7:** run `/audit`. Read the Four Cs gap report. Close one gap.
- **Day 14:** run `/level-up`. Ship one automation.
- **Weekly:** `/level-up`. One shipped artifact per week. It compounds.

See `docs/quickstart-individual.md` or `docs/quickstart-team.md` for the longer walkthrough.
