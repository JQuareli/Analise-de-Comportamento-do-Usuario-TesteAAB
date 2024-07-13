# Analise-de-Comportamento-do-Usuario-TesteAAB
Análise do funil de vendas e os resultados de um teste A/A/B, no aplicativo de uma startup de produtos alimentícios, que teve por objetivo avaliar o impacto de novas fontes no design do aplicativo para otimizar a experiência do usuário e aumentar as conversões.

## Índice

- [Metodologia](#metodologia)
- [Bibliotecas Utilizadas](#bibliotecas-utilizadas)
- [Conclusões](#conclusões)
- [Como Utilizar](#como-utilizar-este-repositório)
- [Possíveis Melhorias](#possíveis-melhorias)

## Metodologia
### Carregamento e Preparação dos Dados

1. **Carregamento dos Dados**:
    - Logs dos eventos: `/datasets/logs_exp_us.csv`

2. **Análise exploratória dos dados - EDA**:
    - Utilizamos a biblioteca ydata_profiling para examinar os principais pontos dos dados e analisar as informações de forma que conseguíssemos identificar os principais pontos a serem explorados. Neste ponto, os dados foram limpos e organizados utilizando a biblioteca Pandas do Python para garantir a precisão das análises subsequentes.

### Relatórios e Cálculo de Métricas

Extraímos alguns gráficos para avaliar os eventos de cada um dos três grupos estavam distribuídos. Foram criados gráficos de barras para identificar a quantidade de eventos por usuário, por dia e por grupo. Também avaliamos o funil de vendas para visualizar cada evento e sua quantidade de usuários.

### Experimento

Este tópico foi dividido em duas partes, a primeira contendo um teste A/A para avaliar se os dois grupos controle são estatisticamente iguais e após isso, realizamos o teste A/A/B, comparando cada um dos grupos controle com o grupo de experimento (B).
Para realizar o teste, utilizamos o teste de proporções Z-teste. Essa escolha foi feita pois tivemos de analisar especificamente a proporção de conversões entre os grupos e se existia alguma diferença estatisticamente significativa entre eles. Analisamos a conversão em cada uma das etapas do funil em relação à anterior.
Por fim, utilizamos o método de False Discovery Rate (FDR) para corrigir os p-valores a fim de aumentar a confiabilidade do experimento, por termos realizado múltiplos testes de significância.


## Bibliotecas Utilizadas

As seguintes bibliotecas Python foram utilizadas para a análise de dados e visualização:

- [Pandas](https://pandas.pydata.org/)
- [NumPy](https://numpy.org/)
- [Matplotlib](https://matplotlib.org/)
- [Seaborn](https://seaborn.pydata.org/)
- [scipy](https://docs.scipy.org/)
- [Ydata Profiling](https://docs.profiling.ydata.ai/latest/)
- [plotly](https://plotly.com/python/)
- [inflection](https://inflection.readthedocs.io/en/latest/)

## Conclusões

Após aplicar todos os testes e aplicando as melhores práticas para reduzir os erros dos testes, vemos que os resultados não alteraram. Isso significa que a alteração da fonte não teve impacto significativo nos dados de conversão em nenhuma etapa do funil, mesmo comparando com os dois grupos de controle.

## Como utilizar este repositório

Para utilizar, basta clonar o repositório e instalar o arquivo requirements.txt em um ambiente Python. Os scripts são bem documentados e podem ser facilmente adaptados para outras análises de dados.

## Possíveis melhorias
Realizar mais análises que verifiquem a confiabilidade do teste estatístico, blindando ainda mais o teste de possíveis erros na separação dos grupos do experimento, podendo interferir nas conclusões tiradas. Além disso, trazer mais informações sobre o teste escolhido, principalmente em relação a escolha feita por utilizar um teste de proporções ao invés de um possível teste qui-quadrado.
