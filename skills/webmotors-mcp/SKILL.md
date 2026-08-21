---
name: webmotors-mcp
description: Skill da REST API do Webmotors na MCP.AI: 6 endpoints em /api/webmotors. Busca de veículos na Webmotors, o maior marketplace automotivo do Brasil. Pesquise anúncios por marca/modelo, veja detalhes completos (specs, fotos, vendedor) e o preço médio de mercado do modelo — o valor real pedido no marketplace, não só a tabela FIPE. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Webmotors — REST API skill

Você tem acesso à **Webmotors** REST API na MCP.AI.

> Busca de veículos na Webmotors, o maior marketplace automotivo do Brasil. Pesquise anúncios por marca/modelo, veja detalhes completos (specs, fotos, vendedor) e o preço médio de mercado do modelo — o valor real pedido no marketplace, não só a tabela FIPE.

## Base URL

```
https://api.mcp.ai/api/webmotors
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/webmotors/category \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/webmotors/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (6)

#### `webmotors_category`

Lista as categorias de veículo da Webmotors. _(POST /api/webmotors/category)_

#### `webmotors_detail`

Detalhe completo de um anúncio. _(POST /api/webmotors/detail)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `slug` | string | Sim | Slug do anúncio (campo `slug` de wm_search; caminho após /comprar). |

#### `webmotors_filters`

Lista as opções de filtro da busca (marcas, modelos e demais facetas) para montar consultas válidas. _(POST /api/webmotors/filters)_

#### `webmotors_location`

Resolve uma localização (cidade/estado/geo) a partir de um texto livre, para filtrar a busca por região. _(POST /api/webmotors/location)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `query` | string | Sim | Texto da localização (ex.: 'campo grande', 'são paulo'). |

#### `webmotors_market_price`

Preço médio de mercado do modelo de um anúncio (id = UniqueId de wm_search). _(POST /api/webmotors/market/price)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `id` | string | Sim | UniqueId do anúncio (campo `id` de wm_search). |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `webmotors_search`

Busca anúncios de veículos na Webmotors. _(POST /api/webmotors/search)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `brand` | string | Não | Marca (ex.: 'honda', 'toyota'). Opcional. |
| `model` | string | Não | Modelo (ex.: 'civic', 'corolla'). Opcional. |
| `path` | string | Não | Caminho de estoque cru (ex.: '/carros/estoque/honda/civic'), alternativa a brand/model. |
| `page` | integer | Não | Página (default 1). |
| `perPage` | integer | Não | Itens por página (default 24, máx 96). |
| `order` | integer | Não | Ordenação da Webmotors (default 1 = relevância). |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_webmotors` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
