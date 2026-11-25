<p align="center"><img src="logo/nana-192.png" width="128" alt="Nana"></p>

# Nana: grocery prices, deals and carts for your AI assistant

Nana is a grocery price assistant from [eezly](https://eezly.com) for **Canada, the United States, France and the United Kingdom**. It answers from real, current shelf prices at the major grocery chains in each country.

Connect Nana to the AI assistant you already use, then ask things like:

- *What do 4 litres of milk cost at each grocery chain in Ontario this week?*
- *Which grocery deals are on this week near ZIP code 10001?*
- *Combien coûtent une baguette, 6 œufs et un litre de lait dans les supermarchés près de 75011 ?*
- *What would milk, a dozen eggs, bread and bananas cost at the supermarkets near SW1A 1AA?*
- *Add 2 litres of milk and a loaf of bread to my grocery cart, then tell me which of my stores is cheapest for the whole cart.*

Nana is a **hosted** MCP server. There is nothing to install or run: you add one address to your assistant.

| | |
|---|---|
| MCP server URL | `https://api.eezly.app/mcp` |
| Transport | Streamable HTTP |
| Sign-in | OAuth 2.1 with PKCE and dynamic client registration; you sign in with your email and a one-time code |
| Registry | [`app.eezly/nana`](https://registry.modelcontextprotocol.io/v0.1/servers?search=app.eezly/nana) in the official MCP Registry |
| Price | Free to use. Nana takes no payments. |

## What Nana can do

- **Prices near you:** what a product costs at the stores near a postal code, ZIP code or postcode, chain by chain.
- **The cheapest store for a whole list:** line by line, with sizes and pack counts read correctly (a box of 6 eggs, a 12-pack).
- **This week's deals:** compared with the regular shelf price.
- **Regions compared:** a basket of staples across regions, by unit price (per litre, kilogram or item).
- **Your list and cart (signed in):** Nana keeps your grocery list and cart across conversations and tells you which of your stores is cheapest for it.

Nana answers only with prices it has actually observed, says when a price is from last week or not available yet, and never guesses a price. Nothing in your cart is removed or replaced unless you ask. Nana stores no allergies or health information.

## Connect Nana

When your assistant first uses Nana, it opens a "Connect Nana" page: enter your email, type the code we send you, and you're connected.

### ChatGPT
Settings → **Apps & Connectors** → *Create* (developer mode), then paste `https://api.eezly.app/mcp` as the MCP server URL.

### Claude (claude.ai and the desktop app)
Settings → **Connectors** → *Add custom connector*, then paste `https://api.eezly.app/mcp`.

### Claude Code
```bash
claude mcp add --transport http nana https://api.eezly.app/mcp
```

### Cursor
In `~/.cursor/mcp.json` (or `.cursor/mcp.json` in a project):
```json
{ "mcpServers": { "nana": { "url": "https://api.eezly.app/mcp" } } }
```

### VS Code (GitHub Copilot agent mode)
In `.vscode/mcp.json`:
```json
{ "servers": { "nana": { "type": "http", "url": "https://api.eezly.app/mcp" } } }
```

### Gemini CLI
In `~/.gemini/settings.json`:
```json
{ "mcpServers": { "nana": { "httpUrl": "https://api.eezly.app/mcp" } } }
```
Or install it as an extension from this repository (see [`gemini-extension.json`](gemini-extension.json)).

### Windsurf
In `~/.codeium/windsurf/mcp_config.json`:
```json
{ "mcpServers": { "nana": { "serverUrl": "https://api.eezly.app/mcp" } } }
```

### Cline
Ask Cline to install the MCP server from this repository; it follows [`llms-install.md`](llms-install.md).

### Any other MCP client
Add a remote (streamable HTTP) MCP server with the URL `https://api.eezly.app/mcp`. The client discovers the sign-in from `https://api.eezly.app/.well-known/oauth-protected-resource/mcp`.

## Partners

Market data for businesses (other apps, retailers, analysts) is available through a separate partner door with credentials from eezly. Contact [support@eezly.com](mailto:support@eezly.com).

## Privacy, terms and support

- Privacy policy: <https://eezly.com/privacy>
- Terms: <https://eezly.com/terms>
- Support: [support@eezly.com](mailto:support@eezly.com) · Privacy: [privacy@eezly.com](mailto:privacy@eezly.com)

This repository holds only the public information needed to connect to Nana (this README, the registry entry and the logo). Nana itself is a hosted service operated by eezly; its source code is not published here.

© eezly. The text of this README is available under the [MIT License](LICENSE). The Nana name and logo are trademarks of eezly and are not covered by the license.
