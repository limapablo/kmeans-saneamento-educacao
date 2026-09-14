# Clusterização de Saneamento e Educação nos Municípios Brasileiros

[![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-K--Means-F7931E?logo=scikitlearn&logoColor=white)](https://scikit-learn.org/)
[![QGIS](https://img.shields.io/badge/QGIS-Análise%20Geoespacial-589632?logo=qgis&logoColor=white)](https://qgis.org/)
[![DOI](https://img.shields.io/badge/DOI-10.29327%2F23189258.1068040-blue)](https://doi.org/10.29327/23189258.1068040)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

> Estudo aplicado de ciência de dados que utiliza **clusterização K-Means** e análise geoespacial para identificar padrões entre municípios brasileiros a partir de indicadores de saneamento e educação.

**Origem acadêmica:** este repositório nasceu do meu **Trabalho de Conclusão de Curso (TCC) do MBA em Data Science & Analytics da USP/ESALQ**. Posteriormente, o trabalho evoluiu para um **artigo científico**, associado ao SIMEP 2025, com DOI **[10.29327/23189258.1068040](https://doi.org/10.29327/23189258.1068040)**.

[Read in English](README.MD)

---

## Visão Geral

A análise de políticas públicas frequentemente exige comparar municípios com realidades muito diferentes em infraestrutura, educação e condições socioeconômicas. Este projeto investiga se técnicas de aprendizado não supervisionado podem organizar parte dessa complexidade em grupos interpretáveis.

A análise aplica **K-Means** a indicadores municipais relacionados a saneamento básico e educação e, em seguida, integra os clusters obtidos à malha municipal brasileira para interpretação espacial.

### Pergunta de pesquisa

> É possível agrupar municípios brasileiros em perfis significativos com base em indicadores de saneamento e educação, de forma a apoiar análises territoriais e de políticas públicas mais direcionadas?

## Objetivos

- Identificar grupos de municípios com perfis semelhantes de saneamento e educação.
- Aplicar um fluxo completo de machine learning não supervisionado sobre dados públicos.
- Interpretar os clusters no contexto socioeconômico real.
- Visualizar a distribuição geográfica dos agrupamentos pelo território brasileiro.
- Demonstrar o uso de ciência de dados como apoio à análise exploratória de políticas públicas.

## Metodologia

O projeto segue um fluxo analítico de ponta a ponta:

1. **Aquisição dos dados** — obtenção de indicadores municipais em fontes públicas.
2. **Preparação dos dados** — limpeza, integração, seleção de variáveis e pré-processamento.
3. **Escalonamento das variáveis** — normalização antes da clusterização baseada em distância.
4. **Clusterização** — aplicação do algoritmo K-Means.
5. **Interpretação dos clusters** — comparação dos perfis municipais segundo os indicadores selecionados.
6. **Integração geoespacial** — associação dos rótulos dos clusters à malha municipal oficial.
7. **Visualização espacial** — construção e interpretação do mapa no QGIS.

## Tecnologias

| Área | Ferramentas |
| --- | --- |
| Análise de dados | Python, Pandas |
| Machine Learning | scikit-learn, K-Means |
| Visualização | Matplotlib, Seaborn |
| Análise geoespacial | QGIS, Shapefile |
| Ambiente de desenvolvimento | Jupyter Notebook |

## Resultado Geoespacial

Os rótulos dos clusters foram associados às geometrias municipais brasileiras, gerando uma camada geoespacial que pode ser explorada no QGIS ou em outra ferramenta SIG.

![Clusters municipais no Brasil](imagens/mapa_clusters.png)

Os artefatos geoespaciais estão disponíveis em `data/geospacial/`, incluindo o projeto do QGIS e os arquivos que compõem o shapefile municipal gerado.

A malha municipal utilizada no estudo foi baseada na **Malha Municipal 2023 do IBGE**.

## Estrutura do Repositório

```text
.
├── data/
│   ├── raw/
│   │   ├── codigo_municipios.xlsx
│   │   └── data_atlas.xlsx
│   └── geospacial/
│       ├── mapa_clusters.qgz
│       └── municipios_com_clusters.*
├── imagens/
│   └── mapa_clusters.png
├── notebook/
│   └── kmeans_saneamento_educacao.ipynb
├── .gitattributes
├── .gitignore
├── CITATION.cff
├── LICENSE
├── README.MD
├── README_PTBR.md
└── requirements.txt
```

## Como Reproduzir

Clone o repositório e crie um ambiente Python:

```bash
git clone https://github.com/limapablo/kmeans-saneamento-educacao.git
cd kmeans-saneamento-educacao
python -m venv .venv
```

Ative o ambiente e instale as dependências:

```bash
pip install -r requirements.txt
```

Abra o notebook:

```bash
jupyter notebook notebook/kmeans_saneamento_educacao.ipynb
```

Para a parte espacial, abra `data/geospacial/mapa_clusters.qgz` no QGIS.

> Este repositório preserva os artefatos analíticos produzidos no estudo acadêmico. A reprodução exata pode depender das versões das bibliotecas e da estrutura das bases públicas disponíveis à época da pesquisa.

## Contexto Acadêmico e Publicação

Este projeto teve origem no **TCC do MBA em Data Science & Analytics da USP/ESALQ**.

O estudo posteriormente evoluiu para um artigo científico associado ao **SIMEP 2025 — Simpósio de Engenharia de Produção**.

- **DOI do artigo:** [10.29327/23189258.1068040](https://doi.org/10.29327/23189258.1068040)
- **Carta de aceite do SIMEP 2025:** [visualizar documento](https://www.even3.com.br/participante/impressao/_impressaocartadeaceite?code=1068040)

Assim, o repositório funciona tanto como **projeto técnico de portfólio** quanto como **registro computacional de uma pesquisa acadêmica**.

## Competências Demonstradas

Do ponto de vista de portfólio, o projeto demonstra experiência em:

- análise exploratória e pré-processamento de dados;
- machine learning não supervisionado;
- escalonamento de variáveis e workflows de clusterização;
- interpretação de resultados de modelos em contexto real;
- integração entre dados tabulares e geoespaciais;
- comunicação de resultados por mapas e visualizações;
- aplicação de ciência de dados a problemas públicos e socioeconômicos.

## Limitações

O K-Means é uma técnica exploratória de clusterização e não estabelece relações causais entre saneamento e desempenho educacional. Os resultados também são sensíveis à seleção de variáveis, ao escalonamento e ao número de clusters escolhido.

Os agrupamentos devem, portanto, ser interpretados como **perfis analíticos**, e não como classificações definitivas ou recomendações diretas de política pública.

## Autor

**Pablo Henrique da Silva Lima**  
MBA em Data Science & Analytics — USP/ESALQ  
Bacharel em Administração — UFRRJ

- [LinkedIn](https://www.linkedin.com/in/limapablo/)
- [GitHub](https://github.com/limapablo)

## Como Citar

Caso este repositório seja útil em trabalhos acadêmicos, cite o artigo associado pelo DOI **10.29327/23189258.1068040** e/ou utilize os metadados disponíveis em [`CITATION.cff`](CITATION.cff).

## Licença

Este repositório é distribuído sob a [Licença MIT](LICENSE). Dados provenientes de instituições públicas externas permanecem sujeitos às condições de uso e atribuição das respectivas fontes.
