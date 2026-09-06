# POWER_BI_CONFIG.md — Configuração do Relatório Power BI

> Referência: relatorio criativo.pbix (desafio Power BI Analyst — DIO)
> Base: Financial Sample.xlsx (700 registros, 16 colunas)

## Tabela e campos
- Tabela: **Financials** (importar Financial Sample.xlsx)
- Campos: Segment, Country, Product, Discount Band, Units Sold, Manufacturing Price, Sale Price, Gross Sales, Discounts, Sales, COGS, Profit, Date, Month Number, Month Name, Year

## Medidas DAX
Ver arquivo `DAX_MEDIDAS.txt`.

---

## PÁGINA 1 — Visão Geral de Vendas

### Card de Indicadores
- Tipo: Cartão (Card) x4
- Medidas: [Total Sales], [Total Units Sold], [Total Profit], [Profit Margin]

### Sales por Segment
- Tipo: Gráfico de Barras
- Eixo Y: Segment
- Valor: [Total Sales]

### Sales ao longo do tempo
- Tipo: Gráfico de Linha
- Eixo X: Date (ou Month/Year)
- Valor: [Total Sales]

### Sales por Produto
- Tipo: Gráfico de Barras
- Eixo Y: Product
- Valor: [Total Sales]

### Sales por Country
- Tipo: Gráfico de Barras
- Eixo Y: Country
- Valor: [Total Sales]

### Mapa de Sales por Country
- Tipo: Mapa (Map / Filled Map)
- Localização: Country
- Tamanho do marcador: [Total Sales]
- Tooltip: Country, Sales, Units Sold, Profit

### Filtro de Data
- Tipo: Slicer de Data (Date range)

---

## PÁGINA 2 — Análise Avançada

### Decomposition Tree
- Tipo: Decomposition Tree (visual nativo do Power BI)
- Analisar: [Total Sales]
- Explicar por: Segment > Country > Product > Discount Band
- Limitação: visual nativo do Power BI; na aplicação web é representado por um Treemap hierárquico.

### Waterfall Chart — Lucro por Mês
- Tipo: Gráfico de Cascata (Waterfall)
- Categoria: Month Name
- Valor: [Total Profit]
- Limitação: representado por barras empilhadas (base transparente + variação).

### Radar Chart — Sales por Segmento
- Tipo: Gráfico de Radar
- Eixo: Segment
- Valores: [Total Sales], [Total Profit], [Total Units Sold]

### Treemap — Sales por Produto
- Tipo: Treemap
- Categoria: Product
- Valor: [Total Sales]

### Chiclet Slicer
- Tipo: Chiclet Slicer (custom visual obtido da loja do Power BI)
- Campo: Product
- Status: implementado no Power BI Desktop.

---

## PÁGINA 3 — Análise Geográfica e Segmentos

### Mapa 1 — Vendas e Unidades Vendidas por País
- Tipo: Mapa
- Localização: Country
- Tamanho do marcador: [Total Sales]
- Cor do marcador: [Total Units Sold]
- Tooltip: Country, Sales, Units Sold, Profit

### Mapa 2 — Lucro por País
- Tipo: Mapa
- Localização: Country
- Tamanho do marcador: [Total Profit]
- Tooltip: Country, Profit, Sales, Units Sold

### Gráfico de Pizza — Lucro por Segmento
- Tipo: Gráfico de Pizza
- Legenda: Segment
- Valores: [Total Profit]
- Detalhe: mostrar percentual do total

---

## Filtros (Slicers) — todas as páginas
- Country, Segment, Product, Date, Year

## Limitações técnicas (aplicação web vs Power BI)
- Mapas coropléticos preenchidos (Filled Map) não reproduzidos fielmente no navegador; usados marcadores circulares (CircleMarker) com Leaflet.
- Decomposition Tree e Chiclet Slicer são visuais nativos/custom do Power BI; representados por equivalentes.
- Interações de drill-through nativas do Power BI não replicadas.
