# Previsão de Preços de Ações com Prophet

Este projeto demonstra como usar a biblioteca Prophet para fazer previsões de séries temporais, especificamente previsões de preços de ações. O exemplo a seguir utiliza dados da ação da Johnson & Johnson (JNJ) para prever os preços de fechamento até o final de 2023.

## Dependências

Para executar este projeto, você precisará instalar as seguintes bibliotecas Python:

- `pandas`
- `yfinance`
- `matplotlib`
- `prophet`

Você pode instalá-las usando o seguinte comando:

```python
bash pip install pandas yfinance matplotlib prophet
```

## Baixando Dados de Ações

O código começa baixando os dados de preços de fechamento da ação da Johnson & Johnson (JNJ) do Yahoo Finance para o período de 2020 a 2023.

```python
python import pandas as pd import yfinance as yf

dados = yf.download("JNJ", start="2020-01-01", end="2023-12-31", progress=False) dados = dados.reset_index()
```

## Preparando os Dados para o Prophet

Os dados são divididos em dois conjuntos: um para treinamento (até julho de 2023) e outro para teste (a partir de agosto de 2023). Os dados de treinamento são preparados para o Prophet, renomeando as colunas para 'ds' (data) e 'y' (valor a ser previsto).

```python
python dados_treino = dados[dados['Date'] < '2023-07-31'] dados_teste = dados[dados['Date'] >= '2023-07-31']

dados_prophet_treino = dados_treino[['Date', 'Close']].rename(columns={'Date': 'ds', 'Close': 'y'})
```

## Criando e Treinando o Modelo Prophet

Um modelo Prophet é criado com padrões semanais e anuais, mas sem padrões diários. Feriados dos EUA são adicionados ao modelo, pois eles podem influenciar o preço das ações. O modelo é então treinado com os dados de treinamento.

```python
python from prophet import Prophet

modelo = Prophet(weekly_seasonality=True, yearly_seasonality=True, daily_seasonality=False) modelo.add_country_holidays(country_name='US') modelo.fit(dados_prophet_treino)
```

## Fazendo Previsões

Um DataFrame com datas futuras é criado para as quais o modelo fará previsões. As previsões são então feitas e plotadas.

```python
python import matplotlib.pyplot as plt

futuro = modelo.make_future_dataframe(periods=150) previsao = modelo.predict(futuro)

plt.figure(figsize=(14, 8)) plt.plot(dados_treino['Date'], dados_treino['Close'], label='Dados de Treino', color='blue') plt.plot(dados_teste['Date'], dados_teste['Close'], label='Dados Reais (Teste)', color='green') plt.plot(previsao['ds'], previsao['yhat'], label='Previsão', color='orange', linestyle='--')

plt.axvline(dados_treino['Date'].max(), color='red', linestyle='--', label='Início da Previsão') plt.xlabel('Data') plt.ylabel('Preço de Fechamento') plt.title('Previsão de Preço de Fechamento vs Dados Reais') plt.legend() plt.show()
```


Este gráfico mostra três linhas: a azul representa o preço real das ações até julho de 2023, a verde mostra os preços reais após essa data, e a laranja mostra o que o Prophet previu. A linha vermelha pontilhada marca onde começam as previsões.

## Conclusão

Este projeto demonstra a facilidade de uso da biblioteca Prophet para fazer previsões de séries temporais, neste caso, previsões de preços de ações. A biblioteca Prophet é conhecida por sua capacidade de lidar com dados com padrões irregulares, tornando-a uma ferramenta valiosa para análise de séries temporais.

