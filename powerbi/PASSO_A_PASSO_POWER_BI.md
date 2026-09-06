# PASSO A PASSO — Reproduzir o Projeto no Power BI Desktop

## 1. Preparação
1. Instale o Power BI Desktop.
2. Baixe os arquivos do projeto (ZIP gerado pela aplicação).
3. Tenha em mãos o arquivo `Financial Sample.xlsx`.

## 2. Importar os dados
1. Abrir Power BI Desktop > **Obter Dados** > **Excel**.
2. Selecionar `Financial Sample.xlsx`.
3. No Navigator, marcar a planilha "Sheet1" e clicar em **Transformar Dados**.

## 3. Power Query (ajustes)
1. Renomear a consulta para **Financials**.
2. Remover a coluna de índice (se houver).
3. Promover a primeira linha como cabeçalho (se necessário).
4. Remover linhas em branco no final.
5. Conferir tipos: Units Sold = Número Decimal, Sales/Profit/COGS = Moeda, Date = Data.
6. Fechar e Aplicar.

## 4. Criar as medidas DAX
1. Aba **Ferramentas de Tabela** > **Nova Medida**.
2. Colar as medidas do arquivo `DAX_MEDIDAS.txt`.

## 5. Reproduzir a Página 1
Siga o arquivo `POWER_BI_CONFIG.md` (seção Página 1) para cada visual.

## 6. Reproduzir a Página 2
Siga o arquivo `POWER_BI_CONFIG.md` (seção Página 2).
- Decomposition Tree e Chiclet Slicer: baixar da loja de visuais do Power BI.

## 7. Criar a Página 3
1. Nova página > renomear para "Análise Geográfica e Segmentos".
2. Adicionar Mapa 1 (Vendas e Unidades por País).
3. Adicionar Mapa 2 (Lucro por País).
4. Adicionar Gráfico de Pizza (Lucro por Segmento).
5. Configurar tooltips conforme o arquivo de configuração.

## 8. Filtros
Adicionar slicers de Country, Segment, Product, Date e Year.

## 9. Revisar títulos e layout
Conferir o checklist em `documentacao/checklist.md`.

## 10. Publicar e entregar
1. Salvar o .pbix.
2. Publicar no serviço do Power BI.
3. Criar repositório GitHub com README, imagens e documentação.
4. Copiar o link do GitHub para a entrega na DIO.
