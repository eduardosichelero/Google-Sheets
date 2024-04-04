# Gráficos de Candlestick com Matplotlib e Plotly

Este guia detalha como criar gráficos de candlestick usando as bibliotecas `matplotlib` e `plotly` em Python, além de demonstrar como adicionar médias móveis e criar subplots. Os gráficos de candlestick são uma ferramenta visual poderosa para analisar dados financeiros, como preços de ações, mostrando a abertura, fechamento, máximo e mínimo de cada período de negociação.

## Instalação e Importação de Bibliotecas

Antes de começar, certifique-se de ter as bibliotecas necessárias instaladas. Se necessário, instale a biblioteca `mplfinance` usando `pip`:

```python
 pip install mplfinance
```

Em seguida, importe as bibliotecas necessárias:
```python
python import pandas as pd import matplotlib.pyplot as plt import matplotlib.dates as mdates import mplfinance as mpf import yfinance as yf import plotly.graph_objects as go from plotly.subplots import make_subplots
 
```
## Baixando Dados de Ações

O código começa baixando dados financeiros do Yahoo Finance usando a biblioteca `yfinance`. Por exemplo, para baixar dados da ação PETR4.SA (Petrobras) para o período de 2023:

```python
python dados = yf.download('PETR4.SA', start='2023-01-01', end='2023-12-31')
 
```

## Renomeando Colunas e Convertendo Índice

Os dados baixados são então manipulados para renomear as colunas e converter o índice (data) em uma coluna:
```python
python dados.columns = ['Abertura', 'Maximo', 'Minimo', 'Fechamento', 'Fech_Ajust', 'Volume'] dados = dados.rename_axis('Data') 
```

## Plotagem de Preços de Fechamento

Um gráfico simples de preços de fechamento é plotado para visualizar a variação do preço ao longo do tempo:
```python
python dados['Fechamento'].plot(figsize=(10,6)) plt.title('Variação do preço por data', fontsize=16) plt.legend(['Fechamento'])
 
```

## Criação do Gráfico de Candlestick

Um gráfico de candlestick é criado usando `matplotlib`. Cada "candle" representa um dia de negociação, mostrando o preço de abertura, fechamento, máximo e mínimo. A cor do candle é determinada pela variação do preço de fechamento em relação ao preço de abertura.

## Adição de Média Móveis

Médias móveis de 7 e 14 dias são calculadas e adicionadas ao gráfico para ajudar na análise de tendências:
```python
python df['MA7'] = df['Fechamento'].rolling(window=7).mean() df['MA14'] = df['Fechamento'].rolling(window=14).mean() 
```

## Formatação do Eixo X

O eixo X é formatado para mostrar as datas de forma legível:
```python
python ax.xaxis_date() ax.xaxis.set_major_formatter(mdates.DateFormatter('%Y-%m-%d')) plt.xticks(rotation=45) 
```

## Criação de Subplots com Plotly

Um exemplo de como criar subplots com `plotly` é mostrado, incluindo um gráfico de candlestick e um gráfico de barras para o volume de transações:
```python
python fig = make_subplots(rows=2, cols=1, shared_xaxes=True, vertical_spacing=0.1, subplot_titles=('Candlesticks', 'Volume Transacionado'), row_width=[0.2, 0.7]) 
```

## Plotagem com mplfinance

Finalmente, o código demonstra como plotar um gráfico de candlestick com médias móveis usando a biblioteca `mplfinance`:
```python
python mpf.plot(dados.head(30), type='candle', figsize = (16,8), volume=True, mav=(7,14)) 
```

Este guia fornece uma visão geral de como criar e visualizar gráficos de candlestick em Python, usando `matplotlib` e `plotly`, e como adicionar médias móveis para análise de tendências. Essas ferramentas são essenciais para analisar dados financeiros e tomar decisões informadas.
