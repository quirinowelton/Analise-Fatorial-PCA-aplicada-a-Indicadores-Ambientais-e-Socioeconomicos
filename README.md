# 🌍 Análise Fatorial (PCA) aplicada a Indicadores Ambientais e Socioeconômicos  
### Distritos da Cidade de São Paulo

Este projeto aplica **Análise Fatorial baseada em Componentes Principais (PCA)** para sintetizar múltiplos indicadores ambientais e socioeconômicos dos **distritos da cidade de São Paulo**, gerando um **indicador sintético** e sua **representação espacial em mapa**.

O estudo foi desenvolvido no contexto do **MBA em Data Science e Analytics – USP/ESALQ**, integrando **estatística multivariada, visualização de dados e análise geoespacial**.

---

## 🎯 Objetivo do Projeto

Responder às seguintes perguntas:

- É possível reduzir a dimensionalidade de indicadores ambientais e socioeconômicos mantendo a maior parte da informação?
- Quais fatores latentes explicam a variação entre os distritos?
- Como representar esses fatores de forma **geográfica**, facilitando a interpretação espacial?

---

## 📁 Base de Dados

- **Fonte:** Atlas Ambiental (dados municipais)
- **Unidade de análise:** Distritos da cidade de São Paulo
- **Variáveis excluídas da PCA:**
  - `cód_ibge`
  - `distritos`

As demais variáveis quantitativas representam indicadores ambientais, sociais e estruturais.

---

## 🛠️ Tecnologias e Bibliotecas Utilizadas

- **Python**
- `pandas`
- `numpy`
- `factor_analyzer`
- `scipy`
- `matplotlib`
- `seaborn`
- `plotly`
- `pyshp` (shapefile)

---

## 🔍 Etapas da Análise

### 1️⃣ Análise Exploratória
- Inspeção do DataFrame
- Estatísticas descritivas das variáveis quantitativas

---

### 2️⃣ Matriz de Correlação
- Cálculo da correlação de Pearson
- Visualização interativa com **Plotly**
- Identificação de multicolinearidade entre indicadores

Um arquivo HTML interativo (`correl_atlas.html`) é gerado como saída.

---

### 3️⃣ Teste de Esfericidade de Bartlett
Avaliação da adequação dos dados à Análise Fatorial:

- **Hipótese nula:** As variáveis não são correlacionadas  
- **Resultado:** p-valor significativo → PCA apropriada  

---

### 4️⃣ Análise de Componentes Principais (PCA)

- Método: **Principal Components**
- Extração inicial de todos os fatores possíveis
- Critério de retenção: **Autovalores > 1 (Critério de Kaiser)**
- Número final de fatores: **2 fatores**

---

### 5️⃣ Variância Explicada

Os dois fatores explicam uma parcela relevante da variância total, permitindo uma representação sintética dos indicadores originais.

Gráfico de barras evidencia:
- Variância individual
- Variância acumulada

---

### 6️⃣ Cargas Fatoriais

- Identificação das variáveis mais associadas a cada fator
- Interpretação conceitual dos fatores
- Visualização por **Loading Plot (Fator 1 × Fator 2)**

---

### 7️⃣ Comunalidades

Avaliação da proporção da variância de cada variável explicada pelos fatores extraídos.

- Valores elevados indicam boa preservação da informação

---

### 8️⃣ Scores Fatoriais

- Cálculo dos scores fatoriais para cada distrito
- Inclusão dos fatores no banco de dados original

---

## 📊 Indicador Sintético e Ranking Territorial

Foi adotado o **Fator 1** como **indicador sintético principal**, representando um eixo socioeconômico/ambiental dos distritos.

> Diferente de uma soma ponderada, o ranking é baseado diretamente no score do primeiro fator.

---

## 🗺️ Análise Espacial – Mapa dos Distritos de São Paulo

### Etapas:

- Importação do shapefile oficial dos distritos
- Organização das coordenadas geográficas
- Associação dos scores fatoriais aos distritos
- Classificação em **6 faixas (quantis)** usando `qcut`
- Aplicação de paleta de cores sequencial (`YlOrBr`)
- Geração do mapa temático com os distritos coloridos

📌 O resultado final é um **mapa coroplético** que facilita a leitura espacial das desigualdades entre distritos.

---

## 📈 Principais Resultados

- Redução eficiente da dimensionalidade
- Extração de fatores interpretáveis
- Construção de indicador sintético territorial
- Integração entre estatística multivariada e análise geoespacial
- Visualização clara das desigualdades regionais

---

## 💡 Competências Demonstradas

- Estatística multivariada (PCA)
- Análise fatorial exploratória
- Interpretação de cargas e comunalidades
- Visualização avançada de dados
- Geoprocessamento com shapefiles
- Pensamento analítico aplicado a políticas públicas e território

---

## 🚀 Possíveis Extensões do Projeto

- Rotação fatorial (Varimax)
- Criação de múltiplos indicadores sintéticos
- Clusterização de distritos
- Séries temporais para análise evolutiva
- Dashboards interativos com mapas (Plotly / Dash)

---

🎓 MBA em Data Science & Analytics – USP/ESALQ  
📊 Data Science | Análise de Dados | Estatística Aplicada | Geoprocessamento
