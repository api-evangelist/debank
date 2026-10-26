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

DeBank is a Web3 portfolio tracker and DeFi data platform operated by DeBank Global Pte. Ltd.
(Singapore). Its developer arm, **DeBank Cloud**, sells access to that data core through a
unit-metered REST API, an OAuth 2.0 sign-in service, and an Official Account messaging API.

## APIs

| API | Base | Contract |
|---|---|---|
| DeBank OpenAPI (Cloud Pro) | `https://pro-openapi.debank.com` | Swagger 2.0, 42 operations, 33 definitions — served live at `/swagger.json` |
| DeBank Connect | `https://api.connect.debank.com` | OAuth 2.0 authorization code, 3 read scopes — documented in prose, no spec |

- Developer portal: <https://cloud.debank.com/>
- Documentation: <https://docs.cloud.debank.com/en>
- API reference: <https://docs.cloud.debank.com/en/readme/api-pro-reference>
- Changelog: <https://docs.cloud.debank.com/en/readme/changelog>
- Terms of service: <https://docs.cloud.debank.com/en/terms-of-service>

## What this profile found

- **A real machine-readable contract at the API host root.** `https://pro-openapi.debank.com/swagger.json`
  returns a complete Swagger 2.0 document — every operation has an `operationId`, a description and
  tags. The docs site never links to it.
- **A published `llms.txt`,** plus a Markdown twin of every documentation page (`.md` suffix), which
  makes the docs unusually agent-readable for this sector.
- **No first-party SDK, CLI or MCP server in any language.** Every DeBank client on npm is
  third-party, and the newest one that wraps the documented API last shipped in 2023.
- **No `/.well-known/` documents on any host,** no agent card, no status page, no security.txt, no
  published compliance program, and no idempotency contract.
- **No public pricing.** Access is metered in prepaid "units" bought from the authenticated
  dashboard; the docs name a "Pro Plan" and its 100 req/s ceiling but publish no unit price.
