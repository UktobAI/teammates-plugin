---
name: operate-with-teammates
description: >-
  Delegate sales prospecting (Adam), customer support knowledge and reply drafts
  (Raya), hiring roles and candidate scorecards (Sara), ad packs, and executive
  planning (AI Co-Founder) across both AI-Run Business and Existing Company
  workspaces on Teammates.ai.
---

# Operate Your Business with AI Teammates

**Read `teammates-best-practices` first.** Keep every teammate separate in identity and job, and format every external draft using the plain-English templates in `teammates-best-practices/references/reply-templates.md`.

## Choosing the Right Teammate

1. **Strategy, weekly priorities, or cross-teammate synthesis (AI Co-Founder):** call `ask_ai_cofounder`.
2. **B2B lead discovery and outbound outreach drafts (Adam, AI Sales):** call `adam_research_leads_and_draft_outreach`.
   - Include target ICP, geography, and message angle.
   - Present discovered leads and staged drafts clearly, and surface the signed 1-tap founder approval URL before anything is sent.
3. **Customer support knowledge search, updates, or reply drafting (Raya, AI Support):** call `raya_knowledge_and_reply_drafts`.
   - Use for updating authoritative company knowledge or drafting grounded customer replies.
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
