# Integrations — the Cadence layer

This is where the Four Cs' **Cadence** lives: the system delivers value with the laptop closed. Two
patterns ship here, each with a generic template and a real worked example from a Weather Company
project (AI Day).

| Folder | What it gives you |
|---|---|
| `webhooks/` | Events from your tools push updates automatically (a push, a status change, a new file) so nobody writes status messages by hand. |
| `dashboard/` | A "show your work" dashboard: a live, visible record of what the system produced and which AI tools touched each deliverable. |

## The one rule of Cadence
**Don't automate a workflow that doesn't work manually first.** Build the capability in the task
layer, run it by hand a few times, then wire a webhook or a schedule so it runs without you. Always
keep a kill switch (a way to pause it) and a human hand on anything that sends or publishes.

## How they reinforce each other
Webhooks feed the dashboard. A push or a status change fires a webhook, the webhook posts to your
comms channel and updates the dashboard, and the dashboard becomes the always-current proof of work.
That loop is what makes a teammate's question get answered by the system, not by you.
