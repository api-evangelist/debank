# DeBank

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

DeBank is a Web3 portfolio tracker and DeFi data platform operated by DeBank Global Pte. Ltd. (Singapore) that indexes wallet balances, protocol positions, NFTs, token prices and transaction history across a large set of EVM and non-EVM chains. Its developer arm, DeBank Cloud, exposes that data core as the DeBank OpenAPI (a Swagger 2.0 contract at pro-openapi.debank.com covering chain, protocol, pool, token, user-portfolio and wallet transaction-simulation endpoints), as DeBank Connect (an OAuth 2.0 authorization-code sign-in that lets a dApp read an authorizing user's base, on-chain and social data), and as an Official Account messaging API for reaching on-chain users through DeBank Hi. Access is metered in prepaid "units" bought from the DeBank Cloud dashboard, keyed by an AccessKey header, with a 14-day free trial and a documented 100 requests/second ceiling on the Pro plan.

**Areas:** Web3 · DeFi · Blockchain · Cryptocurrency · Portfolio Tracking · On-Chain Data · Wallets · token-data · NFT · Ethereum · Authentication · Market Data

## DeBank on APIs.io

Everything profiled for DeBank is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/debank/](https://apis.io/providers/debank/)** — or go straight to one of the APIs or properties below.

### APIs (11)

- [DeBank Connect](https://apis.io/apis/debank/debank-connect/) — OAuth 2.0 authorization-code sign-in for dApps. After a user authorizes, the dApp exchanges the code at api.connect.debank.com/oauth/token using HTTP Basic…
- [DeBank Account API](https://apis.io/apis/debank/debank-account-api/) — The Account API from DeBank — 1 operation(s) for account.
- [DeBank App Protocol API](https://apis.io/apis/debank/debank-app-protocol-api/) — Get app info
- [DeBank Chain API](https://apis.io/apis/debank/debank-chain-api/) — Get chain info
- [DeBank Cloud API](https://apis.io/apis/debank/debank-cloud-api/) — The cloud API from DeBank — 5 operation(s) for cloud.
- [DeBank Official API](https://apis.io/apis/debank/debank-official-api/) — The official API from DeBank — 2 operation(s) for official.
- [DeBank Pool API](https://apis.io/apis/debank/debank-pool-api/) — Get pool info
- [DeBank Protocol API](https://apis.io/apis/debank/debank-protocol-api/) — Get protocol info
- [DeBank Token API](https://apis.io/apis/debank/debank-token-api/) — Get token info
- [DeBank User API](https://apis.io/apis/debank/debank-user-api/) — Get user info such as total balance, token list, and portfolio in each protocol
- [DeBank Wallet API](https://apis.io/apis/debank/debank-wallet-api/) — It is not stable at present. If you want to use it, please contact the official first.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [debank](https://apis.io/servers/debank/debank/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Debank Agentic Access](https://apis.io/agentic-access/debank/debank-agentic-access/)

#### Collections (1)

Postman and Open Collection request collections.

- [DeBank OpenAPI](https://apis.io/collections/debank/open-debank-pro/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Debank Pro Openapi Overlay](https://apis.io/overlays/debank/debank-pro-openapi-overlay/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Debank Authentication](https://apis.io/security/debank/debank-authentication/)
- [Debank Domain Security](https://apis.io/security/debank/debank-domain-security/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Debank Scopes](https://apis.io/scopes/debank/debank-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Debank Plans Pricing](https://apis.io/plans/debank/debank-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Debank Rate Limits](https://apis.io/rate-limits/debank/debank-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://debank.com/)
- [Documentation](https://docs.cloud.debank.com/en)
- [Getting started](https://docs.cloud.debank.com/en/readme/open-api)
- [API reference](https://docs.cloud.debank.com/en/readme/api-pro-reference)
- [Sign up](https://cloud.debank.com/)
- [Changelog](https://docs.cloud.debank.com/en/readme/changelog)
- [Blog](https://debank.com/blog/)
- [Terms of service](https://docs.cloud.debank.com/en/terms-of-service)
- [GitHub](https://github.com/DeBankDeFi)

## API Evangelist rating

**Kin Score 35.8** — thin · rubric 0.24.0 · scored 2026-10-17

| Facet | Score |
|---|---|
| Discoverability | 78.6 |
| Contract quality | 39.0 |
| Contract governance | 4.5 |
| Operational transparency | 39.5 |
| Developer ergonomics | 49.4 |
| Access clarity | 10.5 |

**Agent readiness 23.6** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |

**Regulatory alignment 27.7** — Payments

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/debank/](https://apis.io/providers/debank/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for DeBank: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/debank/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
