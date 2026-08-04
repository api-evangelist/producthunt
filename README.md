# Product Hunt

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Product Hunt is a product discovery platform providing a GraphQL API for accessing product launches, votes, comments, maker profiles, and collection data from the Product Hunt community. Developers can query posts, users, topics, and collections, and with approval, perform write operations such as posting comments and managing goals.

## API

The Product Hunt API v2 is a GraphQL-based interface accessible at `https://api.producthunt.com/v2/api/graphql`. The older V1 REST API has been deprecated.

### Authentication

The API supports three authentication approaches:

- **OAuth User Authentication** - Full OAuth 2.0 flow for user-level access
- **OAuth Client-Only Authentication** - Application-level tokens for read-only public access without user login
- **Developer Token** - Non-expiring token from the API dashboard for simple scripts

### Scopes

| Scope | Description |
|-------|-------------|
| Public | Read-only access to public Product Hunt data |
| Private | Access to user-specific data (requires user authorization) |
| Write | Data modification (requires special approval from Product Hunt) |

### Rate Limits

| Endpoint | Limit | Window |
|----------|-------|--------|
| GraphQL API | 6,250 complexity points | 15 minutes |
| Other V2 Endpoints | 450 requests | 15 minutes |

Rate limit status is returned in response headers: `X-RateLimit-Limit`, `X-RateLimit-Remaining`, and `X-RateLimit-Reset`.

### Available Data

- Product posts and daily launches
- Votes and voting data
- Comments and threads
- User and maker profiles
- Topics and categories
- Collections
- Goals (maker projects)

## Resources

- [API Documentation](https://api.producthunt.com/v2/docs)
- [GraphQL Reference](https://api-v2-docs.producthunt.com/operation/query/)
- [API Explorer](https://ph-graph-api-explorer.herokuapp.com/)
- [API Dashboard](https://www.producthunt.com/v2/oauth/applications)
- [GitHub Repository](https://github.com/producthunt/producthunt-api)
- [GraphQL Schema](https://github.com/producthunt/producthunt-api/blob/master/schema.graphql)

## Plans

- **Developer (Free)** - Non-commercial use, read-only access
- **Write Access** - Approval required from Product Hunt team
- **Commercial** - Contact hello@producthunt.com for licensing terms

See [plans/plans.yml](plans/plans.yml) for full details.

## Contact

- API Support: hello@producthunt.com
- Help Center: https://help.producthunt.com/
