# 🏠 House Prices - Machine Learning

Projeto desenvolvido como trabalho final do curso de Ciência de Dados da Harve, utilizando a competição **House Prices - Advanced Regression Techniques**, do Kaggle.

O objetivo do projeto é aplicar as principais etapas de um projeto de Machine Learning para desenvolver um modelo capaz de prever o preço de venda de imóveis a partir de suas características.

---

## 🎯 Objetivo

Construir e avaliar modelos de regressão para prever a variável `SalePrice`, que representa o preço de venda dos imóveis.

O projeto percorre etapas de análise, preparação dos dados, Feature Engineering, treinamento, validação e geração das previsões finais.

---

## 📊 Dados

Foram utilizados os conjuntos de dados disponibilizados pela competição House Prices do Kaggle.

- **Treino:** 1.460 imóveis com o preço de venda conhecido.
- **Teste:** 1.459 imóveis utilizados para geração das previsões.
- **Variável alvo:** `SalePrice`.

A base possui informações sobre características como área, qualidade geral, ano de construção, garagem, porão, quantidade de banheiros, terreno e diversas outras informações dos imóveis.

---

## 🔎 Etapas do projeto

### 1. Análise exploratória

Foi analisada a distribuição da variável `SalePrice` por meio de histograma e estatísticas descritivas.

A distribuição apresentou assimetria à direita, com maior concentração dos imóveis nas faixas de preço mais baixas e alguns imóveis com valores significativamente superiores.

---

### 2. Análise de Outliers

Os valores extremos das variáveis numéricas foram analisados utilizando:

- Boxplots
- Regra do IQR (Intervalo Interquartil)

Os outliers não foram removidos automaticamente, pois valores extremos podem representar características reais dos imóveis e não necessariamente erros nos dados.

---

### 3. Tratamento de valores nulos

Os valores ausentes foram tratados de acordo com o tipo e significado das variáveis.

Foram utilizadas estratégias como:

- preenchimento de categorias ausentes;
- moda para determinadas variáveis categóricas;
- média para variáveis numéricas.

A variável `SalePrice` foi mantida somente no conjunto de treino, pois representa o valor que o modelo deve prever.

---

### 4. Feature Engineering

Foram criadas novas variáveis a partir das informações existentes para representar melhor algumas características dos imóveis.

Entre elas:

- `Idade`
- `IdadeReforma`
- `AreaTotal`
- `AreaPoraoTotal`
- `TemGaragem`
- `TemPiscina`
- `TemLareira`
- `TemPorão`
- `QualidadeGeral`
- `ProporcaoArea`
- `TotalBanheiros`
- `TotalBsmtFinSF`

---

### 5. Transformação das variáveis categóricas

As variáveis categóricas foram transformadas em valores numéricos utilizando **One-Hot Encoding (Dummies)**.

Após o tratamento, os conjuntos utilizados pelo modelo ficaram com as mesmas features.

---

### 6. Separação entre treino e validação

Os dados com preço conhecido foram divididos em:

- **80% para treinamento**
- **20% para validação**

Essa divisão permitiu avaliar os modelos utilizando dados que não participaram diretamente do treinamento.

---

## 🤖 Modelos avaliados

Foram comparadas três abordagens:

1. Regressão Linear
2. Random Forest
3. Random Forest com transformação logarítmica da variável alvo

As principais métricas utilizadas foram:

- **RMSE (Root Mean Squared Error)**
- **R² (Coeficiente de Determinação)**

---

## 🏆 Resultados

| Modelo | RMSE | R² |
|---|---:|---:|
| Regressão Linear | US$ 66.331 | 0,4264 |
| Random Forest | **US$ 29.301** | **0,8881** |
| Random Forest + Log | US$ 29.887 | 0,8835 |

O **Random Forest** apresentou o melhor desempenho entre os modelos avaliados e foi escolhido como modelo final.

---

## 🔄 Validação Cruzada

Também foi realizada validação cruzada com **5 folds** para avaliar a estabilidade do Random Forest.

Resultados médios:

- **R²:** 0,8640
- **RMSE:** aproximadamente US$ 29.107

Os resultados ficaram próximos aos obtidos na divisão inicial entre treino e validação.

---

## 📈 Importância das Features

A análise de importância das variáveis do Random Forest mostrou maior destaque para características como:

- `AreaTotal`
- `OverallQual`
- `2ndFlrSF`
- `QualidadeGeral`
- `YearBuilt`
- `TotalBanheiros`
- `Idade`

`AreaTotal` e `OverallQual` apresentaram as maiores importâncias relativas para as previsões realizadas pelo modelo.

---

## 🚀 Modelo Final

Após a comparação e validação, o Random Forest foi treinado novamente utilizando todos os **1.460 imóveis do conjunto de treino**.

O modelo foi então utilizado para gerar previsões para os **1.459 imóveis do conjunto de teste**.

As previsões finais estão disponíveis no arquivo:

`results/submission.csv`

---

## 🛠️ Tecnologias utilizadas

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Google Colab
- Jupyter Notebook
- GitHub

---

## 📁 Estrutura do projeto

```text
house-prices-machine-learning/
│
├── README.md
│
├── data/
│   └── README.md
│
├── notebooks/
│   └── Projeto_Final_Harve_House_Prices.ipynb
│
└── results/
    ├── README.md
    └── submission.csv
```

---

## 📚 Aprendizados

Este projeto permitiu aplicar um fluxo completo de Machine Learning:

**Analisar → Limpar → Transformar → Preparar → Treinar → Comparar → Validar → Prever**

Durante o desenvolvimento foram aplicados conceitos de análise exploratória de dados, tratamento de valores ausentes, identificação de outliers, Feature Engineering, transformação de variáveis categóricas, regressão, validação de modelos e análise de importância das features.

---

## 👩‍💻 Autora

**Eduarda Luzia Brezinski**

Projeto desenvolvido como parte do curso de Ciência de Dados da Harve.
