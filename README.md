# Give your agent a real team.

Launch a new **AI-Run Business** or delegate live customer support, B2B sales, and recruiting inside your **Existing Company** directly from your AI agent. Connects over OAuth 2.1 with zero API keys and 1-tap founder approvals on [hq.teammates.ai](https://hq.teammates.ai).

![](assets/teammates-hero.webp)

## What you can ask

Once signed in, talk to your Teammates.ai workspace in plain English or Arabic:

- *"Launch an AI-Run Business website for my boutique Pilates studio in Dubai and shoot the campaign visuals."*
- *"Have Adam find 25 B2B fintech leads in the US and draft personalized outreach for my review."*
- *"Ask Raya to update our shipping policy in support knowledge and draft a reply to this customer ticket."*
- *"Check my Teammates.ai workspace status, Credit balance, and any pending approvals."*

## Five specialist teammates, one workspace

| Teammate | Role | Mode |
| --- | --- | --- |
| **AI Engineer** | Launches live storefronts from a brief or reference site, edits copy and sections, shoots campaign visuals | AI-Run Business |
| **AI Co-Founder** | Workspace status, Credit balance, ad packs, growth planning, founder approvals | Both |
| **Raya** | Autonomous customer support, knowledge base updates, multi-channel reply drafts | Both |
| **Adam** | B2B prospecting, lead research, personalized outbound drafts | Both |
| **Sara** | Hiring role setup, candidate screening, structured interview scorecards | Both |

## Connect from any client

- **Google Antigravity:** Open the **Accounts** tab above and click **Sign in** to authorize your workspace in the browser.
- **Claude:** [Add the Teammates.ai custom connector](https://claude.ai/customize/connectors?modal=add-custom-connector&connectorName=Teammates.ai&connectorUrl=https%3A%2F%2Fapi-hq.teammates.ai%2Fmcp) and sign in with OAuth 2.1.
- **Claude Code:** Run `claude mcp add --transport http teammates https://api-hq.teammates.ai/mcp`
- **Cursor:** Open [teammates.ai/mcp](https://teammates.ai/mcp) for the 1-click installer, or add `https://api-hq.teammates.ai/mcp` as a remote HTTP MCP server.
- **Codex / Gemini CLI:** Add `https://api-hq.teammates.ai/mcp` as a Streamable HTTP MCP server with OAuth 2.1 sign-in.

Or copy and send this prompt to any AI agent:

```text
Connect Teammates.ai MCP to my workspace:
1. Add the remote Streamable HTTP MCP server https://api-hq.teammates.ai/mcp (name: "Teammates.ai", OAuth 2.1 browser sign-in, no API key needed).
2. Trigger the browser sign-in flow and confirm which Teammates.ai tools are ready.
```

## Built for real businesses

- **Zero API keys.** Uses OAuth 2.1 Authorization Code with mandatory PKCE (`S256`) and Dynamic Client Registration at `https://api-hq.teammates.ai/mcp`. Revoke access anytime from your workspace.
- **Safe by default.** Internal research, workspace updates, and drafts run fast. External customer replies, outbound emails, job-board posts, and paid ad spend stage safely and wait for your 1-tap approval on [hq.teammates.ai](https://hq.teammates.ai).
- **Live capability sync.** Pure manifests and plain Markdown skills connected to our live remote MCP server. Zero compiled code, zero telemetry, and every new Teammates.ai capability flows automatically without reinstalling.

## Plans

| Plan | Price | Included |
| --- | --- | --- |
| **Free** | `$0` (no card required) | Your first AI-Run Business launch + 5 starter Credits |
| **Pro** | `$50/mo` | 160 Credits/mo, paid from day one |
| **Business** | `$250/mo` | 900 Credits/mo, paid from day one |
| **Scale** | `$500/mo` | 2,000 Credits/mo, paid from day one |

Full plan details at [teammates.ai/pricing](https://teammates.ai/pricing).

## License & Brand Assets

- **Plugin manifests & skills:** Licensed under the Apache License 2.0 (`Copyright 2026 Uktob, Inc. d/b/a Teammates.ai`).
- **Brand assets & trademarks:** All logos, wordmarks, photography in `assets/`, and Teammates.ai trademarks are **All Rights Reserved** by **Uktob, Inc. d/b/a Teammates.ai** (see `NOTICE`) and are included solely for displaying the official plugin in supported clients and marketplaces.
- **Hosted service:** The Teammates.ai platform and APIs (`hq.teammates.ai`, `api-hq.teammates.ai`) are proprietary services of **Uktob, Inc. d/b/a Teammates.ai**, governed by our [Terms of Service](https://teammates.ai/terms) and [Privacy Policy](https://teammates.ai/privacy).

Questions or partnership inquiries: [support@teammates.ai](mailto:support@teammates.ai)
