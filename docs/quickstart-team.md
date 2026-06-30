# Quickstart — team

Same engine, shared. The goal: everyone runs their own AIOS, and the team shares a source of truth,
connections, and a dashboard.

## Decide the shared spine first
- **One repo or one per person?** Recommended: a shared team repo (this kit) for the source of truth,
  connections, and integrations; each member keeps their own `CLAUDE.md` voice/persona section.
- **Where is the source of truth?** Point `vault/` at a shared Obsidian vault or a synced drive folder
  everyone can read. The vault's `AGENTS.md` rules keep it from becoming a dump.

## Setup
1. One person clones and runs the `SETUP-PROMPT.md`, choosing **team** when asked. They scaffold a
   `context/01-project/` entry per workstream and note who owns what.
2. Each teammate clones, runs `/onboard` for their own voice + priorities, and shares the same
   `connections.md` and `vault/`.
3. Wire the **team connections** once (Slack/Teams, the project tracker, Drive) so everyone's AIOS
   reaches the same live data.

## The team Cadence loop
- A shared **webhook** posts project events to your team channel automatically (see `integrations/webhooks/`).
- A shared **"Created with AI" dashboard** (see `integrations/dashboard/`) makes the work visible to
  everyone, including stakeholders. This is what turns one person's AIOS into an AI-ready team.

## Rituals
- Each person runs weekly `/audit` and `/level-up`.
- One shared decision log (`decisions/log.md`) so direction changes are traceable.
- Quarterly: review `CLAUDE.md` and `connections.md` together; archive what's stale.

> A company where every operator runs a personal AIOS, on a shared source of truth, is a company
> that's actually AI-ready. Start with one person, prove it, then roll out.
