# Consumo de carnes no Brasil (1990–2026)

**O que explica e o que prevê o consumo de carne suína no Brasil?**

Projeto Aplicado da unidade curricular **Estatística Aplicada à Análise de Dados**, Pós-Graduação em Ciência de Dados e Inteligência Artificial (UniSENAI SC).

**Autores:** Vitor Moroni e Geovani Nepomuceno

## Acesse

| Conteúdo | Arquivo |
|---|---|
| Página interativa: os cálculos rodam no navegador e os gráficos respondem aos controles | [`index.html`](index.html) |
| Notebook completo renderizado: todo o código, as saídas, as tabelas e os gráficos | [`notebook.html`](notebook.html) |
| Notebook para executar (Google Colab ou Jupyter) | [`Estatistica_Aplicada_Consumo_Carnes_Brasil.ipynb`](Estatistica_Aplicada_Consumo_Carnes_Brasil.ipynb) |
| Base de dados | [`meat_consumption_worldwide.csv`](meat_consumption_worldwide.csv) |

Com o GitHub Pages ativado, o site fica em `https://<usuario>.github.io/<repositorio>/`.

## O que o projeto faz

1. **Preparação:** filtra o Brasil na base mundial, mantém o consumo per capita (kg/hab/ano) e separa os anos observados (1990–2016) das projeções da OCDE-FAO (2017–2026).
2. **Dados ausentes:** simula falhas de coleta e compara seis métodos de imputação (média, interpolação linear, KNN simples, KNN temporal com k = 3 e k = 5, MICE) em 200 simulações. A interpolação linear teve o menor erro.
3. **Análise descritiva:** medidas de posição, dispersão e forma, histogramas, boxplots e correlações entre níveis e entre variações anuais.
4. **Amostragem:** amostragem estratificada por país na base mundial, comparada com a aleatória simples. O erro padrão caiu 74%.
5. **Probabilidade:** distribuição Normal (com teste de Shapiro-Wilk) e distribuição Binomial.
6. **Inferência:** teste t de Welch com intervalo de confiança, teste de correlação de Pearson e intervalo de confiança para a média mundial.
7. **Modelagem:** cinco modelos de previsão um ano à frente, comparados por validação com origem móvel e pelo desempenho contra uma previsão ingênua.

## Principais resultados

- O consumo de carne suína mais que dobrou entre 1990 e 2016, de 5,4 para 11,5 kg/hab/ano. A mudança de patamar é estatisticamente significativa: o aumento médio ficou entre 3,2 e 4,6 kg/hab (IC de 95%).
- Não há evidência de substituição de curto prazo entre as carnes: as variações anuais não têm correlação significativa.
- A previsão do ano seguinte tem erro típico de cerca de 0,4 kg/hab, mas nenhuma regressão superou a regra de repetir o valor do ano anterior.

## Como executar o notebook

No Google Colab, abra o `.ipynb` e execute todas as células. Se o CSV não estiver na sessão, a primeira célula de código abre o seletor para enviá-lo.

Localmente:

```bash
pip install pandas numpy scipy scikit-learn statsmodels matplotlib seaborn jupyter
jupyter notebook Estatistica_Aplicada_Consumo_Carnes_Brasil.ipynb
```

## Fonte dos dados

OECD/FAO, *OECD-FAO Agricultural Outlook*, indicador *Meat consumption*. Base publicada no Kaggle como *Worldwide Meat Consumption*.
