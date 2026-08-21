# Webmotors

### Webmotors for Claude, ChatGPT and AI agents

Vehicle search on Webmotors, Brazil's largest automotive marketplace. Search listings by make/model, get full details (specs, photos, seller) and the model's average market price — the real asking price on the marketplace, not just the FIPE table.

- 📊 **6 tools**
- 🔒 **Read-only**
- 💬 **Works with any MCP client**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Magic-link login (no password)**

[Portuguese version](README.md) · [Full docs (PT-BR)](docs/)

---

## One-click install

### Claude (Web and Desktop)

[➕ Open in Claude and connect](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

Manual: [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Add custom connector** → name `Webmotors`, URL `https://api.mcp.ai/p_webmotors`.

### Cursor

[➕ Install in Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=webmotors&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF93ZWJtb3RvcnMifQ==)

### VS Code (Copilot Chat)

[➕ Install in VS Code](vscode:mcp/install?name=webmotors&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_webmotors%22%7D)

### Any other MCP-over-HTTP client

```
https://api.mcp.ai/p_webmotors
```

---

## 6 tools

| Tool | Description |
|---|---|
| `webmotors_search` | Busca anúncios de veículos na Webmotors. |
| `webmotors_detail` | Detalhe completo de um anúncio. |
| `webmotors_market_price` | Preço médio de mercado do modelo de um anúncio (id = UniqueId de wm_search). |
| `webmotors_location` | Resolve uma localização (cidade/estado/geo) a partir de um texto livre, para filtrar a busca por região. |
| `webmotors_filters` | Lista as opções de filtro da busca (marcas, modelos e demais facetas) para montar consultas válidas. |
| `webmotors_category` | Lista as categorias de veículo da Webmotors. |

---

## Pricing

See [docs/precos.md](docs/precos.md) (PT-BR).

---

## License

MIT — see [LICENSE](LICENSE). The MCP server at `api.mcp.ai/p_webmotors` is proprietary (hosted); this repo (manifests, docs, skills) is MIT.
