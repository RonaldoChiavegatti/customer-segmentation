# Projeto de Segmentação de Clientes em um Shopping

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

Este projeto visa segmentar clientes de um shopping com base em sua renda anual e pontuação de gastos, utilizando o algoritmo **K-means Clustering**. O objetivo é auxiliar estratégias de marketing personalizadas.

## 📋 Sumário
1. [Coleta de Dados](#coleta-de-dados)
2. [Modelagem](#modelagem)
3. [Conclusões](#conclusões)
4. [Estrutura do Repositório](#estrutura-do-repositório)
5. [Como Reproduzir](#como-reproduzir)

---

## 1. Coleta de Dados <a name="coleta-de-dados"></a>

### Dataset
- **Fonte:** [Mall Customer Segmentation Data](https://www.kaggle.com/datasets/vjchoudhary7/customer-segmentation-tutorial-in-python) (Kaggle).
- **Variáveis Utilizadas:**
  - `Annual Income (k$)` (Renda anual em milhares de dólares)
  - `Spending Score (1-100)` (Pontuação de gastos no shopping).

### Pré-processamento
Os dados foram normalizados para garantir a mesma escala entre as variáveis.

```python
import pandas as pd
from sklearn.preprocessing import StandardScaler

# Carregar dados
data = pd.read_csv("data/Mall_Customers.csv")

# Selecionar features
X = data[['Annual Income (k$)', 'Spending Score (1-100)']]

# Normalizar dados
scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)
