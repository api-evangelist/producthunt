# Product Hunt GraphQL API

The Product Hunt GraphQL API (V2) provides access to the full Product Hunt platform, exposing product launches (Posts), voting data, comments, user profiles, topics, collections, maker groups, and maker projects. Developers can query individual resources by ID or slug, paginate through lists with cursor-based pagination, and filter by criteria such as featured status, date ranges, topic slugs, or user IDs. All data is exposed under a single root Query type with both singular (`post`, `user`, `topic`) and plural (`posts`, `users`, `topics`) entry points.

Authentication uses OAuth 2.0. Applications must be registered in the Product Hunt developer dashboard and obtain an access token. Three scopes are available: `public` (read-only access to published content), `private` (read access to the authenticated user's private data via the `viewer` field), and `write` (mutations such as creating goals, following users, and cheering goals — requires prior approval from Product Hunt). All API calls are made to a single GraphQL endpoint via HTTP POST with a Bearer token in the Authorization header.

The schema defines key object types including `Post`, `User`, `Comment`, `Collection`, `Topic`, `Goal`, `MakerGroup`, `MakerProject`, `Media`, `Vote`, and `Viewer`. Connections follow the Relay cursor-based pagination pattern with `edges`, `pageInfo`, and `totalCount`. Two interfaces are used: `VotableInterface` (implemented by `Post` and `Comment`) and `TopicableInterface` (implemented by `Post` and `Collection`). The Mutation type covers Goal lifecycle management (create, update, mark complete/incomplete, cheer/uncheer) and User follow/unfollow operations.

**Endpoint:** https://api.producthunt.com/v2/api/graphql

**Documentation:** https://api.producthunt.com/v2/docs

**References:**

- Documentation: https://api.producthunt.com/v2/docs
- GettingStarted: https://api.producthunt.com/v2/docs#section/Authentication
- Reference: https://api-v2-docs.producthunt.com/operation/query/
- Schema: https://github.com/producthunt/producthunt-api/blob/master/schema.graphql
- Explorer: https://ph-graph-api-explorer.herokuapp.com/
