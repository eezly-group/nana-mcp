# Installing Nana (for AI coding assistants such as Cline)

Nana is a **hosted, remote** MCP server. Do not clone or build anything; there is no package to install.

1. Add a remote MCP server named `nana` with:
   - URL: `https://api.eezly.app/mcp`
   - Transport: streamable HTTP
2. No API key is needed. On first use the client opens Nana's OAuth sign-in (OAuth 2.1, PKCE, dynamic client registration): the user enters their email and the one-time code they receive.
3. Test it by asking: "What do 4 litres of milk cost at each grocery chain in Ontario this week?"

Example configuration (most clients):

```json
{ "mcpServers": { "nana": { "url": "https://api.eezly.app/mcp" } } }
```

Support: support@eezly.com
