# The Four Cs climb

Build your AIOS in this order. Each layer has a pass test. Don't climb to the next until the current
one passes. (Frameworks: Nate Herk, AIS-OS.)

## 1. Context — the system knows your world
**Pass test:** a fresh Claude session answers "what does this person/business do, and who's involved?"
without browsing.
**How:** run `/onboard`. Fill `context/` and `CLAUDE.md`. Put project specifics in the vault's
`01 - Projects`. This is non-skippable; everything else assumes it.

## 2. Connections — it reaches your stuff
**Pass test:** "what's on my calendar tomorrow and what's due?" returns live data, no copy-paste.
**How:** wire tools into `connections.md`, cheapest first (MCP → script → export). Save a
`references/{tool}-api.md` once per tool so you never re-research it.

## 3. Capabilities — it knows how to do the work
**Pass test:** a short phrase ("draft the weekly update") triggers a multi-step job that produces a
real artifact.
**How:** this is the task layer (`context/02-task/`, `.claude/skills/`). `/level-up` adds one capability
at a time. Make it work by hand before you automate it.

## 4. Cadence — it runs without being asked
**Pass test:** laptop closed, a brief lands in your inbox; a teammate messages the system and gets a
real answer.
**How:** `integrations/` (webhooks + dashboard + schedules). Only automate workflows that already work
manually. Keep a kill switch.

---

**Dependency graph:** Context is first and non-skippable. Connections and Capabilities can build in
parallel. Cadence is last. Run `/audit` weekly to see which layer is your weakest and climb there next.
