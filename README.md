# 💳 Credit Score ML Prediction

> Modelo de Machine Learning para previsão automática de score de crédito de clientes.

---

## 📌 Sobre o Projeto

Este projeto utiliza técnicas de **Inteligência Artificial e Machine Learning** para analisar dados de clientes e prever automaticamente o score de crédito, auxiliando na tomada de decisão de concessão de crédito.

O modelo classifica os clientes em três categorias:

| Classificação | Descrição |
|---|---|
| ✅ **Good** | Score de crédito bom |
| ⚠️ **Standard** | Score de crédito regular |
| ❌ **Poor** | Score de crédito ruim |

---

## 🏗️ Tecnologias Utilizadas

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)

---

## 📁 Estrutura do Projeto

```
credit-score-ml-prediction/
│
├── clientes.csv          # Base de dados histórica para treino
├── inicial.ipynb         # Notebook principal com todo o pipeline
└── novos_clientes.csv    # Dados de novos clientes para previsão
```

---

## ▶️ Como Executar

### 1. Clone o repositório

```bash
git clone https://github.com/Niccassiano/credit-score-ml-prediction.git
cd credit-score-ml-prediction
```

### 2. Instale as dependências

```bash
pip install pandas scikit-learn notebook
```

### 3. Execute o projeto

```bash
jupyter notebook
```

Abra o arquivo **`inicial.ipynb`** e execute as células em ordem.

---

## 📊 Base de Dados

| Arquivo | Descrição |
|---|---|
| `clientes.csv` | Dados históricos utilizados para treino e teste do modelo |
| `novos_clientes.csv` | Dados de novos clientes para geração de previsões |

---

## 🧠 Pipeline do Projeto

### 1. Importação dos Dados

Leitura da base de clientes a partir de um arquivo CSV:

```python
tabela = pd.read_csv("clientes.csv")
```

### 2. Tratamento e Preparação dos Dados

Conversão de variáveis categóricas para numéricas com `LabelEncoder`:

```python
from sklearn.preprocessing import LabelEncoder
```

Colunas tratadas: `profissao`, `mix_credito`, `comportamento_pagamento`

### 3. Separação dos Dados

Divisão entre variável alvo e variáveis preditoras:

- **Y** → `score_credito`
- **X** → demais colunas

```python
from sklearn.model_selection import train_test_split

x_treino, x_teste, y_treino, y_teste = train_test_split(x, y, test_size=0.3)
```

### 4. Treinamento dos Modelos

Dois algoritmos foram testados:

```python
from sklearn.ensemble import RandomForestClassifier
from sklearn.neighbors import KNeighborsClassifier
```

| Modelo | Descrição |
|---|---|
| 🌳 Random Forest | Ensemble de árvores de decisão |
| 📍 KNN | K-Nearest Neighbors |

### 5. Avaliação dos Modelos

Comparação de performance usando acurácia:

```python
from sklearn.metrics import accuracy_score
```

🏆 **Melhor modelo:** `Random Forest`

### 6. Previsão para Novos Clientes

```python
tabela_nova = pd.read_csv("novos_clientes.csv")
previsao = modelo_arvoredecisao.predict(tabela_nova)
```

---



