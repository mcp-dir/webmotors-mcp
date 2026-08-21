# Webmotors

### Webmotors para Claude, ChatGPT e agentes de IA

Busca de veículos na Webmotors, o maior marketplace automotivo do Brasil. Pesquise anúncios por marca/modelo, veja detalhes completos (specs, fotos, vendedor) e o preço médio de mercado do modelo — o valor real pedido no marketplace, não só a tabela FIPE.

- 📊 **6 ferramentas**
- 🔒 **Somente leitura**
- 💬 **Funciona com qualquer cliente MCP**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Login via magic-link (sem senha)**

[English version](README.en.md) · [Documentação completa](docs/) · [Skill pra agentes](skills/)

---

## Instalar em 1 clique

### Claude (Web e Desktop)

A Anthropic unificou a instalação de MCPs em `claude.ai/customize/connectors`. **O mesmo link serve pra Claude Web e Claude Desktop** (basta estar logado):

[➕ Abrir no Claude e conectar](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

**Manual** (se o deeplink não abrir): [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Adicionar conector personalizado** → cole **Nome** `Webmotors` e **URL** `https://api.mcp.ai/p_webmotors`.

### Cursor

[➕ Instalar Webmotors no Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=webmotors&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF93ZWJtb3RvcnMifQ==)

### VS Code (Copilot Chat)

[➕ Instalar Webmotors no VS Code](vscode:mcp/install?name=webmotors&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_webmotors%22%7D)

### ChatGPT, Manus, OpenClaw e mais 40+ clientes

Funciona em qualquer cliente MCP que suporte **MCP over HTTP**. A URL do servidor é sempre:

```
https://api.mcp.ai/p_webmotors
```

Detalhes por cliente: [INSTALL.md](INSTALL.md).

---

## Exemplos de uso

```
Procure um Honda Civic à venda na Webmotors
Qual o preço médio de mercado de um Corolla 2020?
Liste Jeep Compass com fotos e preço
```

---

## 6 ferramentas disponíveis

| Tool | Descrição |
|---|---|
| `webmotors_search` | Busca anúncios de veículos na Webmotors. |
| `webmotors_detail` | Detalhe completo de um anúncio. |
| `webmotors_market_price` | Preço médio de mercado do modelo de um anúncio (id = UniqueId de wm_search). |
| `webmotors_location` | Resolve uma localização (cidade/estado/geo) a partir de um texto livre, para filtrar a busca por região. |
| `webmotors_filters` | Lista as opções de filtro da busca (marcas, modelos e demais facetas) para montar consultas válidas. |
| `webmotors_category` | Lista as categorias de veículo da Webmotors. |

Detalhe de cada tool: [docs/ferramentas.md](docs/ferramentas.md)

---

## Preços

Planos a partir do tier grátis. Veja [docs/precos.md](docs/precos.md).

---

## Privacidade & LGPD

- **Somente leitura**, nenhuma ferramenta altera dados na origem.
- **Sub-processadores**: o LLM host que você escolher (Claude, ChatGPT, Cursor, agente próprio). Lista completa em [docs/privacidade-lgpd.md](docs/privacidade-lgpd.md).
- Os dados retornados pelas tools são enviados ao **LLM host que você escolher**, sub-processador fora do nosso controle. Recomendamos planos com opt-out de treinamento.

---

## Perguntas frequentes

**O servidor é open source?**
O servidor é proprietário (hosted). Este repositório é o wrapper público com manifestos, docs e skills — tudo MIT.

**Posso usar com agente próprio (não Claude/Cursor)?**
Sim — qualquer cliente que suporte MCP over HTTP. URL: `https://api.mcp.ai/p_webmotors`.


---

## Suporte

- 📧 [webmotors@mcp.ai](mailto:webmotors@mcp.ai)
- 🐛 [GitHub Issues](https://github.com/mcp-dir/webmotors-mcp/issues)
- 📄 [docs/](docs/)

---

## Licença

MIT — veja [LICENSE](LICENSE). O servidor MCP em `api.mcp.ai/p_webmotors` é proprietário (hosted); este repositório (manifestos, docs, skills) é MIT.
