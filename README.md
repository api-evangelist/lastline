# Lastline

Lastline was a Santa Barbara, California cybersecurity company founded in 2011, building
high-resolution malware analysis and network detection and response (NDR) technology based on
full-system emulation sandboxing. Its developer-facing surface is the **Lastline Analyst API** — an
asynchronous web API for submitting files and URLs to the Lastline analysis cloud and retrieving
detailed behavioral analysis reports, indicators of compromise and analysis artifacts.

Lastline was acquired by VMware in 2020 and the technology became VMware NSX Network Detection and
Response; VMware was subsequently acquired by Broadcom.

## Current state (probed 2026-07-19)

| Surface | Status |
|---|---|
| `www.lastline.com` marketing site | Retired — no HTTP response |
| `user.lastline.com/portal` customer portal | Live (200), titled "NSX - Network Detection and Response" |
| `analysis.lastline.com/analysis/api-docs/html/` API reference | Live (200) |
| First-party Python client + CLI downloads | Live (200) |
| TLS certificate for `lastline.com` | Issued to Broadcom Inc. |

## API

- **Base URL:** `https://analysis.lastline.com/analysis`
- **Reference:** https://analysis.lastline.com/analysis/api-docs/html/api.html
- **Auth:** HTTP Basic (RFC 7617) or `key` + `api_token` parameters, with an optional session
- **Style:** RPC over HTTP, JSON or XML selected by URL extension, unversioned
- **No OpenAPI definition was ever published.**

## Artifacts

| Artifact | File |
|---|---|
| Authentication | `authentication/lastline-authentication.yml` |
| API conventions | `conventions/lastline-conventions.yml` |
| Error catalog (codes 101–123) | `errors/lastline-error-codes.yml` |
| Data model | `data-model/lastline-data-model.yml` |
| Packages / SDKs | `packages/lastline-packages.yml` |
| CLI | `cli/lastline-cli.yml` |
| Changelog | `changelog/lastline-changelog.yml` |
| Lifecycle | `lifecycle/lastline-lifecycle.yml` |
| Conformance | `conformance/lastline-conformance.yml` |
| Domain security | `security/lastline-domain-security.yml` |
| llms.txt | `llms/lastline-llms.txt` |

## Deliberate absences

Probed and confirmed **not** published, rather than assumed: OpenAPI/AsyncAPI/GraphQL specs, webhooks
or any event surface, MCP server, OAuth scopes, sandbox/test credentials, status page,
`/.well-known/security.txt`, bug bounty program, trust center or compliance certifications, and any
first-party package on npm, PyPI, RubyGems, Maven Central, NuGet, pkg.go.dev, Packagist or crates.io.

Backed by: redpoint-ventures
