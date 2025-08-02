
# 📊 Análise Preditiva de Evasão de Clientes (Churn) — Telecom X - parte 2

Este projeto aborda uma análise preditiva completa sobre a evasão de clientes (churn) na operadora fictícia **Telecom X**, aplicando técnicas de Machine Learning supervisionado. O objetivo é identificar os principais fatores que influenciam o churn e propor estratégias de retenção baseadas em dados.

## 📌 Tópicos

- [📈 Visão Geral](#-visão-geral)
- [🧹 Etapas de Pré-Processamento](#-etapas-de-pré-processamento)
- [🤖 Modelagem Preditiva](#-modelagem-preditiva)
- [📊 Avaliação dos Modelos](#-avaliação-dos-modelos)
- [🔍 Análise de Importância das Variáveis](#-análise-de-importância-das-variáveis)
- [🧠 Conclusão Técnica](#-conclusão-técnica)
- [💡 Estratégias de Retenção](#-estratégias-de-retenção)
- [📂 Arquivos](#-arquivos)
- [🛠️ Requisitos](#-requisitos)
- [👤 Autor](#-autor)

---

## 📈 Visão Geral

A análise foi conduzida com base em um conjunto de dados contendo informações contratuais, demográficas e financeiras de clientes da Telecom X, com o objetivo de **prever a evasão de clientes (churn)** e entender **os principais fatores que influenciam esse comportamento**.

---

## 🧹 Etapas de Pré-Processamento

- Unificação dos dados de diferentes fontes.
- Tratamento de valores ausentes.
- Codificação de variáveis categóricas com `get_dummies()`.
- Criação de novas variáveis derivadas como `Charges.Daily`.
- Verificação e avaliação do balanceamento das classes.
- Normalização das variáveis para modelos sensíveis à escala.

---

## 🤖 Modelagem Preditiva

Dois modelos foram construídos, conforme orientações do desafio:

1. **Regressão Logística** — modelo linear que exige normalização.
2. **Random Forest** — modelo de ensemble que não exige normalização.

Também foram aplicados refinamentos:

- Ajuste de hiperparâmetros no Random Forest.
- Aplicação de `class_weight='balanced'` na Regressão Logística.
- Otimização do threshold de decisão via curva ROC.

---

## 📊 Avaliação dos Modelos

As principais métricas avaliadas para cada modelo foram: **Acurácia, Precisão, Recall, F1-Score e Matriz de Confusão**, tanto em treino quanto em teste.

📌 Modelo com melhor desempenho no conjunto de teste: **Regressão Logística Original** (sem ajuste de threshold), com destaque para **F1-Score** e equilíbrio entre recall e precisão.

---

## 🔍 Análise de Importância das Variáveis

### 🔹 Random Forest

As variáveis mais importantes para a predição de churn foram:

- `Charges.Total` (Gasto total acumulado)
- `Tenure` (Tempo de permanência)
- `Charges.Monthly` e `Charges.Daily`
- `Contract_Two year` / `Contract_One year`
- `PaymentMethod_Electronic check`
- `InternetService_Fiber optic`
- `PaperlessBilling_Yes`

### 🔹 Regressão Logística

Com base nos coeficientes do modelo:

- **Variáveis que diminuem a chance de churn**:
  - `Tenure`, `Contract_Two year`, `TechSupport_Yes`, `PhoneService_Yes`
- **Variáveis que aumentam a chance de churn**:
  - `Charges.Total`, `InternetService_Fiber optic`, `PaperlessBilling_Yes`, `PaymentMethod_Electronic check`

---

## 🧠 Conclusão Técnica

- A **Regressão Logística original se destacou como o modelo mais balanceado**, apresentando **melhor F1-Score** e **maior capacidade de generalização**.
- O **Random Forest apresentou overfitting inicialmente**, mas teve melhorias com ajuste de hiperparâmetros.
- As variáveis mais influentes foram coerentes entre os modelos e destacam fatores como tempo de casa, tipo de contrato e gastos totais.

---

## 💡 Estratégias de Retenção

Com base nos achados, as seguintes ações são recomendadas:

1. **Oferecer contratos de longo prazo** com benefícios e descontos progressivos.
2. **Monitorar clientes com altos gastos**, oferecendo atendimento diferenciado.
3. **Investigar clientes com fatura digital ou débito eletrônico**, por risco elevado.
4. **Fortalecer o suporte técnico**, especialmente para usuários de fibra óptica.
5. **Atuar nos primeiros meses de contrato**, período com maior taxa de churn.

---

## 📂 Arquivos

- `TelecomX_BR.ipynb` — Notebook com toda a análise.
- `dados_tratados.csv` — Base final utilizada na modelagem.
- `TelecomX_dicionario.md` — Dicionário de dados.
- `TelecomX_BR_parte2.pdf` — Relatório final do projeto.
- `TelecomX_importancia_variaveis.png` — Gráficos das variáveis mais relevantes.
- `TelecomX_metricas_modelos.png` — Comparativo visual das métricas de cada modelo.

---

## 🛠️ Requisitos

- Python 3.10+
- pandas, numpy, scikit-learn, matplotlib, seaborn

---

## 👤 Autor

Projeto realizado por **João Costa**, como parte do programa de formação em Ciência de Dados.
