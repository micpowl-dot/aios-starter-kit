# Worked example — AI Day (The Weather Company)

A real AIOS in action, so you can see what "good" looks like before you build your own. AI Day was a
company-wide event run with AI as the operating environment, not a tool picked up here and there.

## What's here
- `operating-manual-EXAMPLE.md` — a real, filled system-layer manual (layer 00). Note how specific it
  is: the operator's voice rules, the standing behaviors, the projects. Yours will look like this
  after `/onboard`, personalized to you.

## What it demonstrates (mapped to the Four Cs)
- **Context.** One GitHub repo was the single source of truth, brief, decisions, specs, all read live
  by the AI. A vault held the human-readable notes. A fresh session could answer "what is this?"
- **Connections.** Calendar, Drive, Slack, and Figma were wired in, so the AI reached tools, not just
  files (six meetings created from one prompt; design tokens read straight from Figma).
- **Capabilities.** A short prompt shipped real artifacts: snap a selfie → an AI-illustrated portrait
  on the wall; design once → all 24 posters rendered across tracks and formats.
- **Cadence.** Webhooks announced progress in Slack on their own; a "Created with AI" dashboard showed
  the work live; portraits auto-sent. Value with the laptop closed.

## The transferable lessons
1. Treat AI as the environment your work runs inside, not a chat window you open.
2. Build the exact tool you need instead of waiting on a vendor or a roadmap.
3. The biggest gains were in the tedious middle: coordination, status, logistics.
4. Automation paid off the instant it ran: one change updated everywhere in seconds.
5. Direct it like a teammate, keep a human hand on anything that sends.

Use the templates in `../../integrations/` to reproduce the webhook and dashboard pieces for your own work.
