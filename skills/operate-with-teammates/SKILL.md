---
name: operate-with-teammates
description: >-
  Check live operations or delegate work to Teammates.ai autonomous teammates
  via the Teammates MCP server. Use whenever the user asks what is happening in
  their support queue, customer inbox, or tickets (Raya), what sales outreach or
  B2B leads are running (Adam), what hiring roles or candidates are active
  (Sara), ad packs, or executive status and priorities (AI Co-Founder) across
  both AI-Run Business and Existing Company workspaces.
---

# Operate Your Business with AI Teammates

**Read `teammates-best-practices` first.** Keep every teammate separate in identity and job, and format every external draft using the plain-English templates in `teammates-best-practices/references/reply-templates.md`.

## Choosing the Right Teammate

1. **Strategy, weekly priorities, or cross-teammate synthesis (AI Co-Founder):** call `ask_ai_cofounder`.
2. **B2B lead discovery and outbound outreach drafts (Adam, AI Sales):** call `adam_research_leads_and_draft_outreach`.
   - Include target ICP, geography, and message angle.
   - Present discovered leads and staged drafts clearly, and surface the signed 1-tap founder approval URL before anything is sent.
3. **Live support queue, ticket inspection, knowledge search, updates, or reply drafting (Raya, AI Support):** call `raya_knowledge_and_reply_drafts`.
   - Use `action="inspect_support_queue"` (read-only) to inspect open tickets, escalated items, resolved 24h count, active conversations, and Raya's autonomous handling status.
   - Use `search_knowledge`, `ingest_note`, or `draft_reply` to query or update authoritative company knowledge or draft grounded customer replies.
   - External customer sends always wait for 1-tap approval on `https://hq.teammates.ai`.
4. **Recruiting roles and cited candidate evaluation (Sara, AI Recruiter):** call `sara_roles_and_candidate_scorecards`.
   - Use for drafting role specs or summarizing cited candidate scorecards.
   - Job-board publishing always waits for 1-tap founder approval.
5. **Marketing ad creatives (Ad Campaigns):** call `create_ad_pack`.
   - Present the generated ad drafts and include the 1-tap founder approval URL before any paid budget runs.

## Output Standard

- Lead with the outcome in plain everyday English (or natural Arabic if the user writes in Arabic).
- Never claim one teammate performed another teammate's job.
- Distinguish clearly between **completed internal work** and **external actions waiting for 1-tap approval on `https://hq.teammates.ai`**.
