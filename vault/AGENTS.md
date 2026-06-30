# Vault — write rules

This is the **source of truth** for human-readable knowledge: projects, sessions, references,
templates, memories. Your AI reads from here and writes here. If you use Obsidian, point this at
your real vault; if not, this folder IS the vault.

## The one rule
**All AI-authored notes, plans, references, and decisions go in here**, in the right lane. Do not
scatter `.md` notes into code repos. Infra files (`README`, `CLAUDE.md`, `AGENTS.md`) stay with
their code; everything else lives here.

## Lanes
| Lane | Holds |
|---|---|
| `00 - Index` | Maps of content; the "start here" note per area. |
| `01 - Projects` | One folder or doc per active project. The WHAT (feeds context layer 01). |
| `02 - Sessions` | Meeting notes, call summaries, working-session logs. |
| `03 - References` | Frameworks, API guides, SOPs, voice samples. Interpreted facts, not raw dumps. |
| `04 - Templates` | Reusable note scaffolds. |
| `05 - Memories` | Durable facts the AI should recall across sessions. |

## Conventions
- **Numbered sequential docs:** `<Project> - NNNNN - <Title> (YYYY-MM-DD)`. Latest = highest number,
  not newest modified date. Increment, never reuse.
- **Frontmatter** on every note (at minimum a one-line `description`).
- **Secrets are references only** (`op://...` or a pointer), never live values in the vault.
- **Interpreted facts only.** Don't paste raw email/Slack archives. Write the fact, link the source.

> Mirrors the EXPANSIONS rule: this should look like a small, well-run business, not a hoarder's
> basement. When you can't find something, consolidate, don't add another folder.
