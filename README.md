# 🚀 Previsibilidade de Surtos de Dengue: Estado de São Paulo (2015-2019)

<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas">
  <img src="https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" alt="Scikit-Learn">
  <img src="https://img.shields.io/badge/Imbalanced--Learn-00599C?style=for-the-badge&logo=python&logoColor=white" alt="Imbalanced-Learn">
</p>

## 📋 Sobre o Projeto
Projeto de Ciência de Dados focado na antecipação e previsão de surtos de dengue nos 645 municípios do Estado de São Paulo (2015–2019). A solução integra microdados epidemiológicos, climáticos e geográficos para transformar dados históricos em alertas preventivos para a gestão de saúde pública (SUS).

> **Diferencial Técnico:** Implementação de **Imputação Espacial por Proximidade** utilizando o algoritmo KNN para associar automaticamente estações pluviométricas às cidades sem medição direta.

---

## 💻 Minha Atuação Técnica no Projeto
Fui responsável pela arquitetura do pipeline de dados, tratamento do desbalanceamento e modelagem do algoritmo baseline:

- **ETL & Integração Espacial:** Cruzamento de 4 bases distintas (DATASUS, DAEE, NASA POWER e IBGE) e criação do esqueleto temporal (38.700 observações) via *Cross Join*.
- **Mapeamento Geográfico (KNN):** Uso de `KNeighborsRegressor` para vincular coordenadas geográficas aos dados pluviométricos mais próximos.
- **Engenharia de Features:** Criação de variáveis defasadas em 1 e 2 meses (`temp_lag`, `chuva_lag`) e padronização com `RobustScaler` sem vazamento de dados (*Data Leakage*).
- **Modelagem Preditiva & Validação:** Treinamento de **Regressão Logística** com sobreamostragem via **SMOTE** e validação temporal com `TimeSeriesSplit`.

---

## 🛠️ Stack Tecnológica

| Categoria | Tecnologias |
| :--- | :--- |
| **Linguagem** | Python 3.x |
| **Manipulação de Dados** | Pandas, NumPy |
| **Tratamento Espacial & ML** | Scikit-Learn, Imbalanced-Learn (SMOTE) |
| **Análise Estatística** | Statsmodels, Seaborn, Matplotlib |

---

## ⚙️ Metodologia e Pipeline

1. **Ajuste Geográfico:** Padronização dos códigos IBGE (6 dígitos) para garantia do gabarito de 645 municípios paulistas.
2. **Integração Espacial:** Associação das estações meteorológicas por latitude/longitude via vizinho mais próximo (KNN).
3. **Engenharia de Recursos:** Cálculo da taxa de incidência por 10.000 hab, binarização da variável alvo `surto` e construção de *lags* climáticos.
4. **Split Cronológico de Dados:** Separação estrita do conjunto de treino (2015–2018) e teste (2019) para simulação de cenários reais de previsão.
5. **Ajuste de Balanço & Treinamento:** Balanceamento das classes raras de surto no treino via SMOTE.

---

## 📊 Fontes de Dados
* **Epidemiológicos:** DATASUS / SINAN (Notificações de Dengue).
* **Pluviométricos:** DAEE (Departamento de Águas e Energia Elétrica SP).
* **Temperaturas:** NASA POWER (Dados Climáticos Municipais).
* **Demográficos:** IBGE (Estimativa Populacional e Coordenadas Geográficas).

---

## 📈 Principais Resultados
* **Identificação de Variáveis Críticas:** A análise de coeficientes (*Odds Ratio*) confirmou a temperatura defasada em 2 meses (`temp_lag_2`) como o fator de maior impacto para a ocorrência de surtos.
* **Detecção Efetiva em 2019:** O modelo baseline identificou corretamente surtos epidemiológicos em 18 municípios paulistas no ano de teste.
* **Estabilidade Temporal:** Validação cruzada temporal (`TimeSeriesSplit`) indicou acurácia média estável de 85% ($\pm 6\%$) nas janelas analisadas.
