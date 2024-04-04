# Imersão_Python_Alura_Analise_de_Dados

### Descrição

Este repositório contém uma coleção de projetos de análise financeira e previsão de séries temporais, utilizando bibliotecas Python como `pandas`, `yfinance`, `matplotlib`, `prophet`, e `mplfinance`. Os projetos abordam a análise de dados de ações, incluindo a criação de gráficos de candlestick, a previsão de preços de fechamento, e uma análise exploratória inicial utilizando Google Sheets e Excel.

### Projetos Incluídos

1. **Análise Exploratória com Google Sheets**
   - **Objetivo**: Realizar uma análise exploratória inicial dos dados financeiros utilizando Google Sheets, aplicando funções como PROCV, SE e ChatGPT para análise.
   - **Funcionalidades**: Utiliza fórmulas para calcular variação percentual, valor inicial, quantidade de ações, variação em reais e determinar o resultado da variação.

2. **Leitura de Dados de Planilha Excel com Pandas**
   - **Objetivo**: Demonstrar como usar a biblioteca `pandas` para ler dados de várias abas de uma planilha Excel, manipulando e analisando os dados em DataFrames separados.
   - **Funcionalidades**: Lê dados de abas específicas da planilha `acoes-pura.xlsx` em DataFrames distintos, permitindo manipulação e análise individual de cada conjunto de dados.

3. **Resumo do Código**
   - **Objetivo**: Realizar uma série de operações de manipulação e análise de dados utilizando `pandas` e `plotly.express`, incluindo importação de dados, manipulação de DataFrames, criação de novas colunas, renomeação de colunas, junção de DataFrames, e análise estatística.
   - **Funcionalidades**: Importa dados de uma planilha Excel, manipula DataFrames, cria novas colunas, renomeia colunas, junta DataFrames, e realiza análise estatística.

4. **Gráficos de Candlestick com Matplotlib e Plotly**
   - **Objetivo**: Demonstrar a criação de gráficos de candlestick para análise de dados financeiros, utilizando `matplotlib` e `plotly`, além de adicionar médias móveis e criar subplots.
   - **Funcionalidades**: Baixa dados de ações do Yahoo Finance, cria gráficos de candlestick, adiciona médias móveis, e cria subplots com `plotly` para visualização de dados.

5. **Previsão de Preços de Ações com Prophet**
   - **Objetivo**: Utilizar a biblioteca `Prophet` para fazer previsões de preços de fechamento de ações, demonstrando a capacidade da biblioteca de lidar com dados com padrões irregulares.
   - **Funcionalidades**: Baixa dados de ações do Yahoo Finance, prepara os dados para o `Prophet`, cria e treina um modelo `Prophet`, faz previsões para datas futuras, e plota os resultados.

### Dependências

Para executar os projetos deste repositório, é necessário instalar as seguintes bibliotecas Python:

- `pandas`
- `yfinance`
- `matplotlib`
- `prophet`
- `mplfinance`

As dependências podem ser instaladas utilizando o seguinte comando:

```python
bash pip install pandas yfinance matplotlib prophet mplfinance
```


### Como Utilizar

1. **Clone o Repositório**: Clone este repositório para o seu ambiente de trabalho.
2. **Instale as Dependências**: Execute o comando de instalação de dependências mencionado acima.
3. **Explore os Projetos**: Navegue pelos diretórios dos projetos e execute os scripts Python para visualizar os resultados das análises e previsões.

