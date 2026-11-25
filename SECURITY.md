# Security Policy

## Reporting a Vulnerability

Please report security issues privately to **security@teammates.ai**. Do not open public GitHub issues for security vulnerabilities.

## Authentication & Data Boundaries

- This plugin connects over HTTPS to `https://api-hq.teammates.ai/mcp` using OAuth 2.1 with mandatory PKCE (`S256`).
- Access tokens are scoped to the specific Teammates.ai workspace authorized by the user and can be revoked at any time.
- External actions (outbound emails, customer replies, job-board posts, and paid ad spend) require explicit founder approval inside `https://hq.teammates.ai`.
