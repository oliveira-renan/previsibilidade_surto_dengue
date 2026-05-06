# 🚀 Previsibilidade de Surtos de Dengue: Estado de São Paulo (2015-2019)

<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas">
  <img src="https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" alt="Scikit-Learn">
</p>

## 📋 Sobre o Projeto
Este projeto acadêmico analisa e prevê surtos de dengue nos 645 municípios de São Paulo. A solução integra dados epidemiológicos, climáticos e geográficos para antecipar picos de incidência.

> **Diferencial Técnico:** Implementação de **Integração Espacial** via algoritmo KNN para estimar dados pluviométricos em regiões sem estações de medição.

---

## 🛠️ Stack Tecnológica

| Categoria | Tecnologias |
| :--- | :--- |
| **Linguagem** | Python |
| **Manipulação** | Pandas, NumPy |
| **Visualização** | Matplotlib, Seaborn |
| **Machine Learning** | Scikit-learn (Logistic Regression, KNN) |

---

## ⚙️ Metodologia e Pipeline
O processo foi estruturado em etapas para garantir a integridade da análise:

*   **Tratamento de Dados:** Normalização dos códigos IBGE e limpeza de nulos.
*   **Feature Engineering:** Cálculo de taxa de incidência e criação de *Lags Temporais* (1 e 2 meses).
*   **Mapeamento Espacial:** Uso de `KNeighborsRegressor` para preenchimento de lacunas geográficas.
*   **Modelagem:** Balanceamento com **SMOTE** e treinamento cronológico (2015-2018) com teste em 2019.

---

## 📊 Fontes de Dados
*   **Epidemiológicos:** DataSUS.
*   **Climáticos:** DAEE e NASA POWER.
*   **Demográficos:** IBGE.

---

## 📈 Principais Resultados
*   **Validação:** Uso de Matrizes de Confusão para prever surtos reais em 2019.
*   **Insights:** A temperatura e a latitude foram identificadas como preditores críticos.
