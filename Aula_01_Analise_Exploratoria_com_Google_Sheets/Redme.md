# Análise Exploratória com Google Sheets

Este projeto foi desenvolvido para realizar uma análise da base de dados da bolsa de valores, explorando o uso do aplicativo Google Sheets. Utilizamos funções como PROCV (ou VLOOKUP), SE (ou IF) e ChatGPT para realizar a análise. Este é um trabalho proposto na Imersão Python: Do Excel à Análise de Dados, promovida pela Alura.

## Fórmulas do Google Sheets

Aqui estão algumas das fórmulas utilizadas no projeto:

- **Variação %**: Esta fórmula calcula a variação percentual do preço das ações.
  Variação % = Var. Dia %/100

- **Valor inicial (R$)**: Esta fórmula calcula o valor inicial das ações com base na variação percentual.
  Valor inicial (R$) = Variação % / (Variação % + 1)

- **Quantidade de ações**: Esta fórmula utiliza a função PROCV para encontrar a quantidade total de ações disponíveis.
  Quantidade de ações = PROCV(Ativo;Total_de_acoes!A:B;2;0)

- **Variação R$**: Esta fórmula calcula a variação em reais das ações.
  Variação R$ = (Valor inicial (R$) - Valor inicial (R$)) * Quantidade de ações

- **Resultado**: Esta fórmula utiliza a função SE (ou IF) para determinar se o preço das ações subiu, desceu ou permaneceu estável.
  Resultado = SE(Variação R$ > 0; "Subiu"; SE(Variação R$ < 0; "Desceu"; "Estável"))

## Conclusão

Através deste projeto, exploramos o poder do Google Sheets para análise de dados, demonstrando como funções como PROCV, SE e ChatGPT podem ser utilizadas para realizar análises complexas de forma eficiente. Este trabalho é um exemplo de como a tecnologia pode ser aplicada para entender melhor o mercado de ações e tomar decisões informadas.
