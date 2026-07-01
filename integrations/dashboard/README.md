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

## The foundation vs the connection
This is the important split, and it is deliberate. The kit ships the **foundation** and leaves the
**connection** to you:

- **Foundation (included):** the dashboard itself. `dashboard-template.html` renders whatever data it
  is given and needs nothing else. The data's shape is defined in `dashboard-data.schema.json`, with a
  filled sample in `dashboard-data.example.json`. Open the template as-is and it works.
- **Connection (you add it):** whatever keeps that data fresh. The dashboard does not care where the
  data comes from, so this is the part that is specific to your tools and lives with you, a webhook
  that appends a row, a small sync script, an export, or just editing the file by hand.

Why ship it this way: the foundation is the same for everyone, but the connection depends on your
stack and your credentials. So you get a working dashboard on day one and wire it to your world when
you are ready. Nothing in the kit assumes your tools.

**Point the template at the data file:** copy `dashboard-data.example.json` to `dashboard-data.json`,
make it yours, then set `FEED_URL = "./dashboard-data.json"` near the top of `dashboard-template.html`.
Leave `FEED_URL` empty to just edit the inline `DATA` array instead.

## Wire it to the Cadence loop (the connection)
When you are ready to automate, have your webhook (see `../webhooks/`) write or append to
`dashboard-data.json` whenever an event lands, so the dashboard updates itself. Keep it matching
`dashboard-data.schema.json` and the template keeps rendering, no changes needed. Manual to start,
automatic once it works.

## Worked example — AI Day (The Weather Company)
Two dashboards ran:
1. A **"Created with AI" board** tracked every deliverable, the tool (Claude Code, Gemini, Firefly,
   ElevenLabs, Figma AI), its role, and the output. The brief's promise was "this conference is
   brought to you by AI, the creative should be too," and the dashboard was the proof, shown live.
2. A **local ops dashboard** ("Command Center") gave the operator a single glance at projects, tasks,
   and what the pipeline did overnight.

The lesson: the dashboard is not a side artifact, it is the story. Build it early; it makes the rest
of the system legible to everyone else.
