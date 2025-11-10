# Predição de Preços de Casas - (Projeto Kaggle)

Este projeto faz parte do meu portfólio de Ciência de Dados.  
Ele reproduz e documenta minha jornada de aprendizado ao participar do **Kaggle - House Prices: Advanced Regression Techniques**, um desafio clássico de regressão.

---

## 🎯 Objetivo
Prever o preço final de venda de casas com base em dezenas de variáveis descritivas (numéricas e categóricas).  
O foco do projeto foi **experimentar, compreender e evoluir** modelos de machine learning supervisionados, comparando desempenho e interpretabilidade.

---

## 🧭 Etapas do Projeto

### 1. Análise Exploratória (EDA)
Explorei os dados buscando entender:
- Quais colunas têm maior impacto no preço (`OverallQual`, `GrLivArea`, `GarageCars`, etc.).
- A presença de outliers e valores ausentes.
- Relações entre variáveis numéricas (identificando multicolinearidade).

Criei gráficos de distribuição e correlação para embasar as decisões de engenharia de features.

---

### 2. Engenharia de Features
Criei novas variáveis combinando informações relevantes, como:
- **`TotalSqFt`** = `GrLivArea` + `TotalBsmtSF`
- **`OverallQual_GarageCars`** = `OverallQual` × `GarageCars`

Essas features aumentaram a capacidade dos modelos simples de capturar relações complexas sem aumentar a dimensionalidade desnecessariamente.

---

### 3. Pré-processamento
Utilizei um **ColumnTransformer** para tratar os dados:
- **Numéricos:** imputação pela mediana e padronização.
- **Categóricos:** imputação pelo valor mais frequente e OneHotEncoder com `handle_unknown='ignore'`.

Todo o processo foi encapsulado em pipelines, garantindo reprodutibilidade.

---

### 4. Modelagem
Testei e comparei três modelos principais:

| Modelo | Motivo da Escolha | Observações |
|--------|-------------------|--------------|
| **Decision Tree Regressor** | Primeiro baseline interpretável | Forneceu insights rápidos sobre importância de variáveis |
| **Random Forest Regressor** | Melhor estabilidade e redução de overfitting | Resultados mais consistentes após otimização de hiperparâmetros |
| **XGBoost Regressor** | Modelo final, captura relações não-lineares com regularização | Obteve melhor performance global |

---

### 5. Avaliação
- Métrica utilizada: **RMSLE** (Raiz do Erro Quadrático Médio do Log).
- Avaliação por **cross-validation (10 folds)** para estabilidade.
- Resultado de referência: **RMSLE = 0.12926** no Kaggle.

---

### 6. Principais Aprendizados
- A importância de iterar com modelos simples antes de partir para modelos complexos.
- O impacto real da engenharia de features bem pensada.
- A eficiência de pipelines completas para garantir reprodutibilidade e clareza no código.
- Como documentar um projeto técnico de forma legível para recrutadores e colegas de área.

---

## 🧩 Tecnologias Utilizadas
- **Python 3.11**
- **Pandas**, **NumPy**, **Matplotlib**, **Seaborn**
- **Scikit-learn**
- **XGBoost**


