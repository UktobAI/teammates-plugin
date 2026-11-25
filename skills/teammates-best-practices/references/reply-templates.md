# Plain-English Reply Templates

Fill in each `{...}` placeholder and keep the rest crisp, human, and jargon-free. Never include raw JSON, internal IDs, HTTP status codes, or snake_case error strings. Leave the `>` quote marks out of the final reply.

## 1. Sign-In Required (Plugin Not Connected)

Never show raw JSON or TOML config files. Guide the user to 1-click OAuth 2.1 sign-in.

> Your Teammates.ai workspace is not signed in yet.
>
> To connect in one click (no API keys needed):
> 1. Click **Sign in** on the Teammates.ai plugin (or open the plugin's Accounts tab).
> 2. Choose the Teammates.ai workspace you want to connect on `https://hq.teammates.ai/mcp-connect`.
> 3. Come back here and I will run `{what they asked for}` right away.
>
> Setup guide: https://teammates.ai/mcp

## 2. Sign-In Expired or Authorization Refused

Stop and do not loop retries.

> Your Teammates.ai session needs a fresh sign-in before I can run `{what they asked for}`.
>
> Reconnect your workspace from the Teammates.ai plugin Accounts tab, then tell me when you are ready and I will pick right back up.

## 3. Existing Company Mode Gate (AI-Run Website Tool Requested)

Use whenever `operating_mode` is Existing Company and the user asks to launch, clone, edit, or shoot a website with AI Engineer.

> Your connected workspace (`{workspace name}`) is set up as an **Existing Company** workspace. Website launches, live edits, and campaign shoots with **AI Engineer** are available in **AI-Run Business** workspaces only.
>
> What you can do right now:
> - **Use your Existing Company teammates.** Ask **AI Co-Founder** for an executive plan, **Adam** for B2B leads and outreach drafts, **Raya** for support knowledge and reply drafts, **Sara** for hiring roles and scorecards, or draft an **Ad Pack**.
> - **Switch to an AI-Run Business workspace.** Reconnect the Teammates.ai plugin and pick (or create) an AI-Run Business workspace on `https://hq.teammates.ai/mcp-connect`.

## 4. Pending 1-Tap Founder Approval Staged

Use whenever a teammate drafts an external email, customer reply, job post, domain action, or paid ad campaign. Make it unmistakable that nothing was sent or spent yet.

> **{Teammate name}** drafted `{concise summary of what was staged}`. Nothing has been sent or published yet.
>
> - **Status:** Waiting for your 1-tap approval
> - **Review and approve:** {signed approval URL on https://hq.teammates.ai}
>
> Once you approve it there, Teammates.ai will carry it out automatically.

## 5. Insufficient Credits or Plan Upgrade Needed

Report only the live Credit balance returned by the server. Never invent trials, discounts, or bonus Credits.

> `{workspace name}` does not have enough Credits left to finish `{what they asked for}` (current balance: `{exact Credit count}` Credits on `{plan name}`).
>
> You can top up Credits or upgrade your plan in Workspace Billing on `https://hq.teammates.ai`:
> - **Free ($0, no card required):** first AI-Run Business launch plus 5 starter Credits
> - **Pro ($50/mo):** 160 Credits/mo
> - **Business ($250/mo):** 900 Credits/mo
> - **Scale ($500/mo):** 2,000 Credits/mo
>
> Full plan comparison: https://teammates.ai/pricing

## 6. Out of Scope

Use when the user asks for something the Teammates MCP tools do not perform (for example, bypassing founder approval gates, editing Stripe billing directly, or merging separate teammates into one persona).

> The Teammates.ai plugin does not currently support `{what they asked for, in their words}`. `{Short sentence noting where they can handle it on https://hq.teammates.ai, if applicable.}`
>
> What I can do from here instead:
> - **{Concrete outcome 1}.** {One short sentence describing what you will run.}
> - **{Concrete outcome 2}.** {One short sentence describing what you will run.}

## 7. Too Broad or Missing Key Details

Use when a request lacks the minimal brief needed to produce a real outcome (for example, "Launch my business" with no industry/offer, or "Find leads" with no target buyer).

> To get a strong result on the first pass, share a bit more detail about `{what is missing}`.
>
> You can reply with something like:
> - **Launch a site (AI Engineer):** "{concrete example prompt}"
> - **Find B2B leads (Adam):** "{concrete example prompt}"
> - **Update support docs (Raya):** "{concrete example prompt}"

## 8. Transient Error or Timeout (After One Retry)

Use only after retrying a transient failure once. Never make up data.

> Teammates.ai could not complete `{what they asked for}` right now because the service returned a temporary error. Nothing was sent or changed.
>
> Try again in a moment, or check your workspace directly at `https://hq.teammates.ai`.
