# 🧠 K-Means para Tomada de Decisão em Saneamento e Educação

Este projeto aplica técnicas de clusterização (K-Means) em dados de municípios brasileiros, com foco nos indicadores de acesso ao saneamento básico e desempenho educacional. O objetivo é propor um modelo de apoio à priorização de políticas públicas com base em dados.

## 🔍 Problema

Como identificar grupos de municípios com características semelhantes em relação à infraestrutura de saneamento e desempenho educacional, de modo a apoiar decisões públicas mais eficazes?

## 📊 Abordagem

1. **Coleta de dados**: dados extraídos de fontes públicas (IBGE).
2. **Pré-processamento**: limpeza, normalização e seleção de variáveis.
3. **Modelagem**: aplicação do algoritmo K-Means.
4. **Análise dos clusters**: interpretação dos grupos formados.
5. **Visualização**: gráficos para apoiar os insights obtidos.

## 🧪 Tecnologias e Ferramentas

- Python
- Pandas
- Scikit-learn
- Seaborn / Matplotlib
- Jupyter Notebook
- QGIS (para visualização geoespacial)

## 🌍 Visualização Geoespacial

Para representar visualmente os clusters gerados pelo K-Means, foi utilizado o **QGIS**, um software de código aberto para análise geoespacial. Através dele, foi criado um mapa do Brasil com os agrupamentos municipais, facilitando a interpretação regional dos dados.

Essa visualização reforça a aplicabilidade do modelo em contextos reais de planejamento territorial e políticas públicas.

### 📍 Dados Geoespaciais

Para a criação do mapa com os clusters de municípios, foram utilizados arquivos **Shapefile** oficiais de municípios brasileiros, posteriormente integrados com os resultados do modelo de K-Means.

A partir disso, um novo shapefile foi gerado contendo o rótulo do cluster para cada município. Esse material está disponível na pasta `data/geoespacial/` e pode ser utilizado no **QGIS** ou em outras ferramentas SIG para reprodução da análise geoespacial.

📂 `data/geoespacial/`

- `municipios_com_clusters.shp` — shapefile com os clusters atribuídos
- `mapa_clusters.qgz` — projeto QGIS com o mapa final dos clusters

🔗 Arquivo shapefile original obtido em: [IBGE - Malha Municipal 2023](https://geoftp.ibge.gov.br/organizacao_do_territorio/malhas_territoriais/malhas_municipais/municipio_2023/Brasil/BR_Municipios_2023.zip)

## 📁 Estrutura do repositório

```
├── notebooks/
│   └── kmeans_saneamento_educacao.ipynb
├── data/
│   ├── raw/
│   └── geoespacial/
├── imagens/
│   └── mapa_clusters.png
├── documentacao/
│   ├── TCC_MBA_DataScience_USP_ESALQ_PabloLima.pdf
│   └── Artigo_SIMEP2025_KMeans_Saneamento_Educacao.pdf
├── README.md
└── README_EN.md
```

## 📈 Resultados Esperados

- Grupos de municípios com padrões similares de infraestrutura e desempenho.
- Base para ações mais direcionadas em políticas públicas.

## 📄 Documentação complementar

Este projeto é derivado do Trabalho de Conclusão de Curso do MBA em Data Science & Analytics da USP/ESALQ e do artigo aceito para publicação no Simpósio de Engenharia de Produção (SIMEP 2025).

📌 [`TCC_MBA_DataScience_USP_ESALQ_PabloLima.pdf`](documentacao/TCC_MBA_DataScience_USP_ESALQ_PabloLima.pdf)\
📌 [`Artigo_SIMEP2025_KMeans_Saneamento_Educacao.pdf`](documentacao/Artigo_SIMEP2025_KMeans_Saneamento_Educacao.pdf) *(a ser publicado oficialmente em maio de 2025)*\
📌 [`Carta de Aceite - SIMEP 2025`](https://www.even3.com.br/participante/impressao/_impressaocartadeaceite?code=1068040)

## 👤 Autor

**Pablo Henrique da Silva Lima**\
MBA em Data Science & Analytics - USP/ESALQ\
Bacharel em Administração - UFRRJ

---



🗓️ Artigo aceito para publicação no SIMEP 2025 ✨

