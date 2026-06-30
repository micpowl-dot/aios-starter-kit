# Dashboard — show your work, live

A "show your work" dashboard is the always-current proof of what your AIOS produced: every
deliverable, which AI tool touched it, and its status. It turns "trust me, we used AI" into a
visible record, and it is the surface a teammate (or an exec) can glance at instead of asking you.

Two flavors, both useful:
- **Created-with-AI tracker** — one row per deliverable: name, the AI tool/role, the output, status.
  Proof and accountability. Great for teams and stakeholders.
- **Personal ops dashboard** — your day at a glance: active projects, what's due, what the system did
  while you were away. Great for a solo operator.

## Turn-key version
`dashboard-template.html` is a single self-contained file (no build, no server needed, open it in a
browser). Edit the data array at the top, or point it at a JSON feed your webhook writes. Host it
anywhere static (or just open the file locally).

## Wire it to the Cadence loop
Have your webhook (see `../webhooks/`) append a row whenever an event lands, so the dashboard updates
itself. Manual to start, automatic once it works.

## Worked example — AI Day (The Weather Company)
Two dashboards ran:
1. A **"Created with AI" board** tracked every deliverable, the tool (Claude Code, Gemini, Firefly,
   ElevenLabs, Figma AI), its role, and the output. The brief's promise was "this conference is
   brought to you by AI, the creative should be too," and the dashboard was the proof, shown live.
2. A **local ops dashboard** ("Command Center") gave the operator a single glance at projects, tasks,
   and what the pipeline did overnight.

The lesson: the dashboard is not a side artifact, it is the story. Build it early; it makes the rest
of the system legible to everyone else.
