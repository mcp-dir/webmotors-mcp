# Ferramentas

Webmotors expõe 6 ferramentas (todas somente leitura).

### 1. `webmotors_search`
**Input**: `brand` (opcional), `model` (opcional), `path` (opcional), `page` (opcional), `perPage` (opcional), `order` (opcional)

Busca anúncios de veículos na Webmotors.

### 2. `webmotors_detail`
**Input**: `slug`

Detalhe completo de um anúncio.

### 3. `webmotors_market_price`
**Input**: `id`, `ids` (opcional)

Preço médio de mercado do modelo de um anúncio (id = UniqueId de wm_search).

### 4. `webmotors_location`
**Input**: `query`

Resolve uma localização (cidade/estado/geo) a partir de um texto livre, para filtrar a busca por região.

### 5. `webmotors_filters`
**Input**: nenhum input

Lista as opções de filtro da busca (marcas, modelos e demais facetas) para montar consultas válidas.

### 6. `webmotors_category`
**Input**: nenhum input

Lista as categorias de veículo da Webmotors.

## Prompts de exemplo

```
Procure um Honda Civic à venda na Webmotors
Qual o preço médio de mercado de um Corolla 2020?
Liste Jeep Compass com fotos e preço
```
