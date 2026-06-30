# Webhooks — automatic status, no one asking

A webhook is an automatic announcement one app sends another the moment something happens, so
nobody has to go check. Like a bank texting you the second a charge hits your card. Wire one and
your tools tell you (and your AIOS) about events instead of you polling them.

## The generic pattern
```
[ source event ]  ->  [ webhook endpoint ]  ->  [ action ]
 git push,             a small handler          post to Slack/Teams,
 status change,        (n8n, a serverless        update the dashboard,
 new file, deadline     function, or a script)   append to the vault
```

Start with ONE source and ONE action. Expand later.

## Setup (any stack)
1. Pick a **source** that emits events (GitHub, your task tracker, your form tool, a calendar).
2. Stand up a **handler**. Easiest options, cheapest first:
   - **n8n / Make / Zapier** — no code, a "Webhook" trigger node into a "Slack/Teams" node.
   - **Serverless function** (Vercel/Cloudflare) — receives the POST, formats it, forwards it.
   - **Script** — a tiny endpoint that re-posts. See `connections.md` for where to register it.
3. Point the source's webhook setting at your handler URL.
4. **Test with a real event** before trusting it. Then add it as a row in `connections.md`.

## Worked example — AI Day (The Weather Company)
A GitHub repo webhook fired on key events and posted to a Slack channel automatically:
- Phase completions, logo approval, and vendor-deadline changes surfaced on their own.
- Real catch: when a print deadline shifted and created a conflict, Slack flagged it before anyone
  noticed by hand.
- Pattern used: **the system announced its own progress; no one wrote status updates.**

Config sketch (n8n):
```
Trigger:  Webhook (POST from GitHub repo events: push, release, issue)
Filter:   event in {phase-complete, approval, deadline-change}
Format:   build a one-line human message + link
Action:   Slack -> #project-channel   (and: append a line to the dashboard data)
```

> Keep a kill switch: a single toggle (an env flag or a disabled node) that pauses the webhook
> without redeploying. And never let a webhook send anything externally without a human gate.
