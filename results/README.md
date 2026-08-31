# 📊 Resultados

Esta pasta contém os resultados gerados pelo modelo final de Machine Learning.

## 🏆 Modelo selecionado

Após a comparação dos modelos, o **Random Forest** apresentou o melhor desempenho no conjunto de validação.

- **RMSE:** aproximadamente US$ 29.301
- **R²:** 0,8881

Na validação cruzada com 5 folds:

- **RMSE médio:** aproximadamente US$ 29.107
- **R² médio:** 0,8640

## 📄 Arquivos

### `submission.csv`

Arquivo contendo as previsões realizadas pelo modelo final para os **1.459 imóveis do conjunto de teste**.

O arquivo possui duas colunas:

- `Id` - identificador do imóvel.
- `SalePrice` - preço de venda previsto pelo modelo.

Este arquivo foi gerado no formato necessário para submissão na competição House Prices do Kaggle.
