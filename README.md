
## 🎯 Objetivo do Projeto

- **Análise Exploratória (EDA)**: entender a base de dados, tipos de variáveis, correlações e distribuições.  
- **Clusterização e Outliers**: segmentar condições de plantio via PCA+KMeans e detectar cenários atípicos com IsolationForest.  
- **Modelagem Preditiva**: treinar 5 modelos de regressão supervisionada (`LinearRegression`, `Ridge`, `RandomForestRegressor`, `GradientBoostingRegressor`, `SVR`) para prever rendimento.  
- **Boas Práticas de ML**: pipelines reprodutíveis, validação cruzada (`RepeatedKFold`), `GridSearchCV` leve para ajuste de hiperparâmetros, métricas adequadas.  
- **Conclusão e Relatório**: seção final com pontos fortes, limitações e sugestões de próximos passos.


## 🔧 Requisitos

Para executar o notebook, instale os pacotes necessários (Python 3.10+):

```bash
pip install pandas numpy matplotlib scikit-learn joblib

```
## 📊 Principais Resultados
| Modelo           | RMSE\_cv | RMSE\_test | MAE\_test   | R²\_test |
| ---------------- | -------- | ---------- | ----------- | -------- |
| LinearRegression | 8414.80  | 4527.90    | 3315.96     | 0.9947   |
| Ridge            | 8307.77  | 4599.03    | 3328.58     | 0.9945   |
| RandomForest     | 7739.66  | 4630.46    | **2619.19** | 0.9944   |
| GradientBoosting | 7890.13  | 5447.90    | 2720.43     | 0.9923   |
| SVR              | 83351.93 | 71292.83   | 38948.07    | -0.31    |


RandomForestRegressor → menor MAE, modelo mais robusto para previsão.

LinearRegression → excelente ajuste (R² ≈ 0.9947), sugere padrão linear forte.

SVR → desempenho ruim (descartado).

Clusterização revelou grupos distintos de rendimento; outliers foram identificados para investigação.

## 📝 Pontos Fortes

- Pipeline completo: pré-processamento, imputação, normalização, e modelos em um único objeto.
- Reprodutibilidade: random_state fixo e seção com versões de bibliotecas.
- Visualizações: histogramas, matriz de correlação, PCA, boxplots por cluster, gráfico de importância de variáveis.
- Entrega pronta: código comentado, células de Markdown organizadas, artefatos salvos.

## ⚠️ Limitações

- Busca de hiperparâmetros reduzida (para execução rápida); tuning maior pode melhorar ensembles.
- Clusterização feita em PCA 2D; métodos mais avançados (UMAP/t-SNE) podem explorar melhor a estrutura dos dados.

## 👨‍💻 Autores
- Projeto desenvolvido por [Rodrigo Portugal Santos, Carlos Daniel Silveira Do Nascimento, Mauricio Jose Ferlin Tonnera] para a FIAP — Fase 5 do curso.
