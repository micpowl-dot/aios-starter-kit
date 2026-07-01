# aios-starter-kit

A turn-key **AI Operating System (AIOS)** starter kit for Claude Code. Clone it, paste one
prompt, and you (or your team) get an always-on operating brain: a single source of truth your
AI reads, the connections to reach your real tools, and automations that deliver value with the
laptop closed.

This kit **builds on (https://github.com/nateherkai/AIS-OS)** (MIT) and
extends it with three things a real working system needs:

1. **A source-of-truth vault** committed into the repo (an Obsidian-style knowledge base your AI reads and writes).
2. **Webhooks** — events from your tools push updates without anyone asking.
3. **A "show your work" dashboard** — proof of what the system produced, live.

It is organized as **context-engineering layers** (the Karpathy way): the AI loads context in a
deliberate order, `system -> project -> task`, so a fresh session is grounded before it acts.

> Credit: the Three Ms and Four Cs frameworks, the `/onboard` `/audit` `/level-up` rituals, and the
> base structure are Nate Herk's (AIS-OS, MIT). This kit packages them with a vault, integrations,
> worked examples, and a one-paste setup. Use freely; keep the attribution; don't repackage the
> frameworks as your own.

---

## The litmus test

> **While you're not at your desk, your AIOS observes one real-world event and produces an output
> that's faster and more accurate than what you'd produce yourself.**

Every piece of this kit rolls up to that test.

## Turn-key in five minutes

1. **Clone** this repo to a folder on your machine.
2. **Open it in Claude Code** and paste the prompt in [`SETUP-PROMPT.md`](SETUP-PROMPT.md). It runs the
   `/onboard` interview, fills your context, points the vault at your notes, and walks you through
   wiring one webhook and one dashboard from the worked examples.
3. **Use it for a week** with real questions and real decisions.
4. **Day 7:** run `/audit`. **Day 14:** run `/level-up` and ship your first automation. Then weekly.

Solo or team: the setup asks which, and scaffolds accordingly. See `docs/`.

## The two frameworks (Nate Herk)

- **Three Ms — how you think.** Mindset (to what extent can AI leverage this?), Method (find the
  constraint, then Eliminate / Automate / Delegate), Machine (build boring, reliable workflows).
- **Four Cs — what you build, climb in order.** Context (the system knows your world) -> Connections
  (it reaches your tools) -> Capabilities (a short phrase ships an artifact) -> Cadence (it runs
  without being asked).

Full deep-dive: [`references/3ms-4cs-framework.md`](references/3ms-4cs-framework.md).

## Layout

```
aios-starter-kit/
├── SETUP-PROMPT.md          paste this into Claude Code to bootstrap everything
├── CLAUDE.md                operating manual (filled by /onboard); documents the layer load order
├── aios-intake.md           7-question source-of-truth for /onboard
├── connections.md           registry of every tool your AIOS can reach
│
├── context/                 context-engineering layers, loaded in order
│   ├── README.md            how the layers load (system -> project -> task)
│   ├── 00-system/           always-on: the operating brain + frameworks
│   ├── 01-project/          per-project context (the WHAT) + template
│   └── 02-task/             how a request becomes an artifact (the skills/capabilities)
│
├── references/3ms-4cs-framework.md
├── decisions/log.md         append-only record of what was decided and why
├── archives/                old stuff. don't delete, move here
├── .claude/skills/          /onboard · /audit · /level-up
│
├── vault/                   source-of-truth mirror (Obsidian-style). AGENTS.md has the write rules
├── integrations/
│   ├── webhooks/            generic webhook template + AI Day example
│   └── dashboard/           "show your work" dashboard template + example
├── examples/ai-day/         a real, filled AIOS (The Weather Company AI Day) to learn from
└── docs/                    quickstarts (solo + team), the Four Cs climb
```

`EXPANSIONS.md` tells you what to add as you grow. The rule: your AIOS should look like a small,
well-run business, not a hoarder's basement.

## License

MIT. Frameworks © Nate Herk; see `LICENSE` and the attribution above.
