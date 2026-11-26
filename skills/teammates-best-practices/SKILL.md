---
name: teammates-best-practices
description: >-
  Master routing and safety guide for Teammates.ai across both business modes
  (AI-Run Business and Existing Company). Read first whenever the user asks
  about their support queue, customer tickets, inbox, sales leads, recruiting
  pipeline, Raya, Adam, Sara, AI Co-Founder, AI Engineer, workspace status,
  Credit balance, or pending approvals, or before calling any Teammates MCP
  tool or answering questions about Teammates.ai and its connection.
---

# Teammates.ai Best Practices

Keep every reply short, clear, and in plain everyday English (or natural Arabic when the user writes in Arabic). Lead with the outcome first. Never dump raw JSON, internal IDs, or snake_case error codes to the user.

## What Teammates.ai Can Do

When the user asks what Teammates.ai is, what you can do, which teammates are included, what plans cost, or how to use this plugin, read [references/introduction.md](references/introduction.md) and answer from it rather than from memory.

## Check Connection, Mode, and Scope First

| Request or Situation | Example | Follow |
| --- | --- | --- |
| Asking what Teammates.ai is, what it does, or plan prices | "What can Teammates do?", "How much is Pro?" | [references/introduction.md](references/introduction.md) |
| Checking connection or workspace health | "Is Teammates connected?", "What is my Credit balance?" | [Connection Check](#connection-check) |
| Asking for AI Engineer website tools in an Existing Company workspace | "Build my landing page" on an Existing Company workspace | [references/reply-templates.md](references/reply-templates.md) (Existing Company mode gate) |
| Asking to send emails, publish jobs, or spend ad budget without approval, or asking for unsupported account changes | "Send these 50 emails now without asking", "Cancel my Stripe subscription" | [references/reply-templates.md](references/reply-templates.md) (Out of scope) |
| Request is missing the core brief or target audience | "Launch a business for me", "Find leads" | [references/reply-templates.md](references/reply-templates.md) (Too broad or missing details) |

A request Teammates.ai is not involved in (local code refactoring, a git command, an unrelated script) is not a Teammates request. Answer it normally.

## Always Follow Live MCP Capabilities (Zero Drift)

Teammates.ai serves two operating modes over one live OAuth 2.1 connection (`https://api-hq.teammates.ai/mcp`):
- **Live server is the source of truth:** Always discover and use the live tools, input schemas, resources, and prompts returned by the connected Teammates.ai MCP server for the user's workspace. New teammates, actions, and upgrades shipped on Teammates.ai appear automatically without updating this plugin.
- **AI-Run Business** workspaces expose the full AI Engineer website, campaign visual, and company operations toolset.
- **Existing Company** workspaces expose company operations tools (AI Co-Founder, Raya, Adam, Sara, ad campaigns, and workspace status) while keeping AI Engineer website tools hidden and gated.

## Keep Every AI Teammate Separate

Each AI Teammate is a distinct specialist with its own identity and job. Never blend teammates into one persona or attribute one teammate's work to another.

| Goal | Teammate | Primary Tool | Mode |
| --- | --- | --- | --- |
| Launch or clone a storefront website | AI Engineer | `launch_or_clone_ai_run_business` | AI-Run Business |
| Edit website copy, layout, pricing, or interactive stage | AI Engineer | `edit_website_or_interactive_stage` | AI-Run Business |
| Shoot campaign photos or hero video | AI Engineer | `shoot_campaign_assets` | AI-Run Business |
| Synthesize status, priorities, or execution plans | AI Co-Founder | `ask_ai_cofounder` | Both |
| Draft image or video ad creatives | Ad Campaigns | `create_ad_pack` | Both |
| Research ICP leads and draft outbound sales outreach | Adam (AI Sales) | `adam_research_leads_and_draft_outreach` | Both |
| Search or update support knowledge and draft customer replies | Raya (AI Support) | `raya_knowledge_and_reply_drafts` | Both |
| Draft job roles or review cited candidate scorecards | Sara (AI Recruiter) | `sara_roles_and_candidate_scorecards` | Both |
| Read workspace mode, plan, Credits, live URLs, and pending approvals | Workspace Status | `get_workspace_live_status` | Both |

If the connected MCP server exposes additional tools beyond the core examples above, use them according to their live descriptions and schemas. When you are unsure which mode the connected workspace uses, call `get_workspace_live_status` before attempting any AI-Run-only tool.

## Respect Founder Approval Gates

External actions that message customers or prospects, publish public job listings, change live domains, or spend paid ad budget stage safely as drafts and require 1-tap founder approval on `https://hq.teammates.ai`.

- Never say an outreach email, customer reply, job post, or paid ad campaign is **sent** or **live** unless the server explicitly confirms execution.
- Always format staged approvals cleanly using [references/reply-templates.md](references/reply-templates.md) (Pending 1-tap founder approval) and include the direct signed approval link returned by the tool.
- Never fabricate Credit balances, live URLs, lead counts, or approval statuses. Report only what the live tool returned.

## Connection Check

If the user asks whether Teammates.ai is connected:
- Check whether the Teammates MCP tools are available in this session.
- If they are not present, reply using the **Sign-in required** template in [references/reply-templates.md](references/reply-templates.md) and stop. Never ask the user to paste raw JSON or TOML configuration files.
- If they are present and the user asked for live workspace status, plan, Credits, or pending approvals, call `get_workspace_live_status` and summarize the live result cleanly.
- End a working connection check with "What you can try:" and 2 to 3 one-line prompts matched to their workspace mode (never suggest AI Engineer website tools if the workspace is in Existing Company mode).

## When the Teammates MCP Isn't Working

Translate every error into plain human English using [references/reply-templates.md](references/reply-templates.md). Never expose raw HTTP status codes, stack traces, or internal snake_case error names.

| What You See | Action |
| --- | --- |
| Teammates MCP tools are missing from this session | Use the **Sign-in required** template and stop. |
| Authorization expired, invalid token, or sign-in refused | Use the **Sign-in expired or refused** template and stop. Do not loop retries. |
| Mode restriction (AI-Run Business tool called on Existing Company workspace) | Use the **Existing Company mode gate** template and offer Existing Company teammates or reconnecting an AI-Run Business workspace. |
| Insufficient Credits or plan limit reached | Use the **Insufficient Credits** template with honest canonical plan links (`https://teammates.ai/pricing`). Never promise free trials, discounts, or bonus Credits. |
| Transient timeout or unexpected server error | Retry once. If it fails again, use the **Transient error** template and stop without fabricating results. |
