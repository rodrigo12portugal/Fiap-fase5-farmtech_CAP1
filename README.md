## 👨‍💻 Autores
- Projeto desenvolvido por [Rodrigo Portugal Santos, Carlos Daniel Silveira Do Nascimento, Mauricio Jose Ferlin Tonnera] para a FIAP — Fase 5 do curso.

## **Meta de entrega 1**

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

## Video de explicação entrega 1
https://youtu.be/-HcJFriFmyM


## **Meta de entrega 2**

## Região São Paulo — sa-east-1 (Brasil)

Instancia de Maquina EC2, t4g.micro com 2 vCPUs, 1 GiB de RAM, até 5 Gbps ← atendendo perfeitamente as configurações -> Valor de $9.78 p/mês

<img width="1524" height="223" alt="image" src="https://github.com/user-attachments/assets/fc580c75-b26e-47d4-9339-2169d96895dd" />

<img width="1467" height="130" alt="image" src="https://github.com/user-attachments/assets/3362b479-067f-4ef3-8911-b160f64b7d02" />

<img width="347" height="619" alt="image" src="https://github.com/user-attachments/assets/0b1b55b8-4f04-45fd-89a2-af45d567aa6b" />

- 50 GB de armazenamento (HD) de Throughput Optimized HDD(st 1) ← atendendo perfeitamente as configurações -> Valor de $4.30 p/mês
<img width="1466" height="612" alt="image" src="https://github.com/user-attachments/assets/8c86b2f6-a885-4e73-bf46-ec9c73cf3b88" />

- **Resultado Calculo total**
 $ 14.08 p/mês na região São Paulo

<img width="414" height="109" alt="image" src="https://github.com/user-attachments/assets/cac60057-2639-4ea2-89fc-e886ac211a9b" />


## Região Virgínia do Norte — us-east-1 (EUA)

- Instancia de Maquina EC2, t4g.micro com 2 vCPUs, 1 GiB de RAM, até 5 Gbps ← atendendo perfeitamente as configurações -> Valor de $6.13 p/mês

<img width="1529" height="246" alt="image" src="https://github.com/user-attachments/assets/b723e6c4-4fd0-444e-8b8a-3fdce0ec1009" />

<img width="1428" height="133" alt="image" src="https://github.com/user-attachments/assets/cb7ff02a-b31c-4a90-905a-1133f6535e7a" />

<img width="344" height="608" alt="image" src="https://github.com/user-attachments/assets/d10e5958-cb5c-4c84-bc69-531e8a178291" />

- 50 GB de armazenamento (HD) de Throughput Optimized HDD(st 1) ← atendendo perfeitamente as configurações -> Valor de $2.25 p/mês
<img width="1472" height="630" alt="image" src="https://github.com/user-attachments/assets/a3995774-7a38-4323-a2b6-978dcb58f392" />

- **Resultado Calculo total**
 $ 8.38 p/mês na região de Virgínia do Norte
<img width="406" height="116" alt="image" src="https://github.com/user-attachments/assets/c5c70454-0b7b-4a7f-95d2-98ef17c27833" />



- **Conclusão:**
A análise de preços mostra que a região Virgínia do Norte (us-east-1) é a mais econômica para hospedar a API e o modelo de Machine Learning, com custo aproximado de US$ 8.38/mês, enquanto a região São Paulo (sa-east-1) chega a cerca de US$ 14.08/mês.
Portanto, a recomendação é utilizar a instância t4g.micro com 50 GB de armazenamento HDD (sc1) na Virgínia do Norte, garantindo desempenho adequado com menor custo operacional.
