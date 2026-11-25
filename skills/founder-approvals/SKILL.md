---
name: founder-approvals
description: >-
  Inspect live Teammates.ai workspace status, operating mode, plan, Credit
  balance, live website URLs, and pending founder approvals awaiting 1-tap
  sign-off on hq.teammates.ai.
---

# Workspace Status and Founder Approvals

**Read `teammates-best-practices` first.** Give the founder a crisp 10-second executive briefing grounded strictly in live server data.

## Steps

1. Call `get_workspace_live_status` (and read the Pending Founder Approvals resource when available).
2. Present the live briefing in four clean bullets:
   - **Workspace & Mode:** workspace name, operating mode (AI-Run Business or Existing Company), and active plan.
   - **Credits:** exact current Credit balance returned by the server.
   - **Live Links:** active preview or custom-domain URLs (only when returned by the server).
   - **Pending Approvals:** exact count and plain-English summary of each queued external action (outbound outreach, customer reply, job post, or ad spend) with its direct 1-tap `https://hq.teammates.ai` approval link.
3. If there are zero pending approvals, state that clearly and suggest one concrete next step that matches the workspace's operating mode (never suggest AI Engineer website tools on an Existing Company workspace).
4. Never fabricate balances, URLs, or approval counts, and never dump raw JSON or internal IDs.
