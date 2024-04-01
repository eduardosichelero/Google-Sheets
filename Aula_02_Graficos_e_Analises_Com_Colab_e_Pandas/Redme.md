# Leitura de Dados de Planilha Excel com Pandas

Este guia detalha como usar a biblioteca `pandas` em Python para ler dados de várias abas de uma planilha Excel chamada `acoes-pura.xlsx`. A planilha contém várias abas, cada uma com informações diferentes, e o código lê cada uma dessas abas em um DataFrame do pandas separado.

## Importação da Biblioteca Pandas

Primeiro, a biblioteca `pandas` é importada, que é uma ferramenta poderosa para manipulação e análise de dados em Python.

```python
python import pandas as pd
```

## Leitura da Aba "Principal"

Uma variável chamada `df_principal` é criada para armazenar os dados da aba "Principal" da planilha `acoes-pura.xlsx`. A função `pd.read_excel()` é usada para ler os dados da aba especificada. O caminho do arquivo é fornecido como argumento, juntamente com o nome da aba desejada.


```python
python df_principal = pd.read_excel("/content/acoes-pura.xlsx", sheet_name="Principal") df_principal

```

## Leitura da Aba "Total_de_acoes"

Da mesma forma, uma variável chamada `df_total_acoes` é criada para armazenar os dados da aba "Total_de_acoes" da planilha. A função `pd.read_excel()` é chamada novamente, desta vez especificando a aba "Total_de_acoes".


```python
python df_total_acoes = pd.read_excel("/content/acoes-pura.xlsx", sheet_name="Total_de_acoes") df_total_acoes
```

## Leitura da Aba "Ticker"

A variável `df_ticker` é criada para armazenar os dados da aba "Ticker" da planilha. A função `pd.read_excel()` é usada novamente, desta vez especificando a aba "Ticker".


```python
python df_ticker = pd.read_excel("/content/acoes-pura.xlsx", sheet_name="Ticker") df_ticker
```

## Leitura da Aba "ChatGPT"

Por fim, uma variável chamada `df_chatgpt` é criada para armazenar os dados da aba "ChatGPT" da planilha. A função `pd.read_excel()` é chamada pela última vez, desta vez especificando a aba "ChatGPT".

```python
python df_chatgpt = pd.read_excel("/content/acoes-pura.xlsx", sheet_name="ChatGPT") df_chatgpt
```

## Conclusão

Este guia demonstra como usar a biblioteca `pandas` para ler dados de várias abas de uma planilha Excel em Python. Cada aba é lida em um DataFrame separado, permitindo que os dados sejam manipulados e analisados individualmente. Isso é útil para tarefas de análise de dados onde diferentes conjuntos de dados precisam ser tratados de maneiras diferentes.

