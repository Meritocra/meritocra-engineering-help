# Meritocra Engineering Help for Grok Build

This package configures Grok Build to use Meritocra Engineering Help, a public
remote MCP for provider-neutral software-delivery triage and explicitly
confirmed project requests.

## What it does

- Triage a production or delivery problem from the context you provide.
- Assess a short engineering brief and identify missing context.
- Produce a provider-neutral next-step checklist.
- Submit a project request only after you review the exact brief and explicitly
  confirm it.
- Check the minimal status of a request only with its private case token.

## Security and data boundary

This package contains no scripts, hooks, local filesystem access, local process,
telemetry, credentials, or environment-variable access. It configures one
network destination only:

`https://meritocra.com/api/engineering-help/mcp`

The remote service does not access your repositories, files, accounts,
assistant memory, or chat history. It receives only the fields you explicitly
place in a tool call. Do not include passwords, API keys, access tokens, private
keys, customer exports, payment details, or private source code.

`meritocra_submit_request` is a write action. It requires an explicit
`confirmed: true`, an email address, and an idempotency key. An accepted request
may notify Meritocra Project Desk and cannot be withdrawn; do not invoke it
until the reviewed brief is correct.

## Support and terms

- Setup and data-handling guide: <https://meritocra.com/mcp.md>
- Privacy notice: <https://meritocra.com/privacy/>
- Terms: <https://meritocra.com/terms/>
- Support: <https://meritocra.com/support/>

The source package is MIT licensed. The remote Meritocra service is governed by
its public terms.

## Marketplace status

This repository is a public source package, not proof of an xAI marketplace
listing. An xAI catalog submission must pin a public commit from this official
Meritocra repository and pass the marketplace's review and CI checks.
