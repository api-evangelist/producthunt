# Product Hunt

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
