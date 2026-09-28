# Buscador de Preços e Links de Livros

Automação em Python que lê uma lista de livros a partir de uma planilha Excel e busca, para cada item, o link e o preço em duas fontes diferentes, salvando o resultado atualizado em uma nova planilha.

## Como funciona

1. Carrega a lista de livros (nome, autor e categoria) a partir de `Produtos.xlsx`.
2. Para cada livro, pesquisa primeiro no [Project Gutenberg](https://www.gutenberg.org/) (livros de domínio público, gratuitos).
3. Se não encontrar no Gutenberg, pesquisa como alternativa no [Books to Scrape](https://books.toscrape.com/), filtrando pela categoria informada.
4. Registra o link e o preço encontrados (ou nulo, se não encontrado em nenhuma das fontes).
5. Salva o resultado em `Produtos_atualizados.xlsx`.

## Tecnologias utilizadas

- **Python 3.13**
- **Selenium** — automação de navegador e extração de dados das páginas
- **pandas** — leitura e escrita das planilhas Excel
- **openpyxl** — suporte à leitura/escrita de arquivos `.xlsx`
- **webdriver-manager** — gerenciamento automático do driver do navegador

## Como executar

1. Clone o repositório e instale as dependências:

   ```bash
   pip install selenium pandas openpyxl webdriver-manager
   ```

2. Coloque um arquivo `Produtos.xlsx` na raiz do projeto, com as colunas:

   | nome | autor | categoria |
   |------|-------|-----------|

3. Execute o notebook (`Projeto.ipynb`) célula por célula, ou converta para script `.py` e execute normalmente.

4. Ao final, o arquivo `Produtos_atualizados.xlsx` será gerado com as colunas `link` e `preco` preenchidas.

## Possíveis melhorias futuras

- Substituir as esperas implícitas por `WebDriverWait` explícito do Selenium.
- Adicionar tratamento de erros mais granular (timeout, elemento não encontrado, item duplicado).
- Empacotar como executável (`.exe`) via PyInstaller.
- Adicionar testes automatizados para as funções de busca.

## Autor

Marcelo Fantin — [GitHub](https://github.com/MarceloFantin)
