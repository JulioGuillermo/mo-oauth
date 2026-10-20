# mo-oauth

The OAuth client metadata document of mo, served by GitHub Pages at
<https://julioguillermo.github.io/mo-oauth/client-metadata.json>.

An MCP server that takes client metadata documents reads it when mo signs in
with that address as its `client_id`, instead of mo registering a client:

```toml
[mcp.jira]
url = "https://mcp.atlassian.com/v2/mcp"
oauth = { client_id = "https://julioguillermo.github.io/mo-oauth/client-metadata.json" }
```

mo is a public client: it signs in with PKCE, has no secret, and the browser
comes back to a free port of localhost, as the loopback addresses here allow.
`client_id` must stay the exact address the document is served at.
