---
name: launch-ai-business
description: >-
  Launch, customize, and shoot campaign visuals for an AI-Run Business website
  using Teammates.ai AI Engineer. Use when the user wants to start a new
  business from a brief, clone a reference layout into a live storefront, edit
  website copy, pricing, or interactive sections, or generate campaign
  photography and ad drafts.
---

# Launch an AI-Run Business with AI Engineer

**Read `teammates-best-practices` first.** If you have not read `teammates-best-practices` in this conversation, load it first for workspace mode rules, teammate separation, and plain-English reply templates.

## Step 1: Confirm Workspace Mode

Call `get_workspace_live_status`.
- If the workspace is in **Existing Company** mode, stop before calling any AI-Run-only tool. Reply using the **Existing Company mode gate** template in `teammates-best-practices/references/reply-templates.md`.

## Step 2: Launch or Clone the Storefront

If the user has not described what the business sells, who it serves, or its location/language, ask for those details using the **Too broad or missing details** template before calling the tool.

Call `launch_or_clone_ai_run_business` with:
- A crisp, concrete `brief` describing the offer, target customers, location, language (English or Arabic), and any user-supplied pricing.
- Optional `reference_url` only when the user explicitly shared a reference website.

Report the live preview URL, status, and any confirmation steps in plain English. Never invent prices, discounts, or URLs not returned by the server.

## Step 3: Iterate on Copy, Pricing, or Interactive Sections

When the user asks to change headlines, pricing, layout, calculators, or interactive stages, call `edit_website_or_interactive_stage` with the exact requested changes. Never invent prices or discounts the user did not supply.

## Step 4: Shoot Campaign Visuals and Stage Ad Packs

- Call `shoot_campaign_assets` for cohesive brand photography or hero video (or pass a specific `asset_id` to regenerate one single visual without redoing the entire shoot).
- Call `create_ad_pack` when the user wants ready-to-approve ad creatives. Always report staged ad packs using the **Pending 1-tap founder approval** template; paid ad spend never runs until the founder approves on `https://hq.teammates.ai`.
