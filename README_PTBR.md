# Clusterização de Saneamento e Educação nos Municípios Brasileiros

[![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-K--Means-F7931E?logo=scikitlearn&logoColor=white)](https://scikit-learn.org/)
[![QGIS](https://img.shields.io/badge/QGIS-Análise%20Geoespacial-589632?logo=qgis&logoColor=white)](https://qgis.org/)
[![DOI](https://img.shields.io/badge/DOI-10.29327%2F23189258.1068040-blue)](https://doi.org/10.29327/23189258.1068040)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

> Pesquisa aplicada de ciência de dados utilizando **clusterização K-Means, análise de correlação e interpretação geoespacial** para identificar padrões de saneamento e educação nos municípios brasileiros.

**Origem acadêmica:** este repositório foi desenvolvido a partir do meu **TCC do MBA em Data Science & Analytics da USP/ESALQ**. Posteriormente, o trabalho evoluiu para o artigo científico **“Saneamento e Educação: Explorando Padrões em Municípios Brasileiros através de Clusterização”**, apresentado no XIII Simpósio de Engenharia de Produção (SIMEP) em 2025.

**Artigo publicado:** [10.29327/23189258.1068040](https://doi.org/10.29327/23189258.1068040)  
**Case study no portfólio:** [limapablo.com/projects/sanitation-education-clustering/](https://limapablo.com/projects/sanitation-education-clustering/)  
[Read in English](README.MD)

---

## Pergunta de Pesquisa

> É possível agrupar municípios brasileiros em perfis significativos com base em indicadores de saneamento e educação, de forma a evidenciar desigualdades territoriais e apoiar análises de políticas públicas mais direcionadas?

## Dados e Escopo

A amostra analítica contém **5.556 municípios brasileiros** após a remoção de observações com dados ausentes.

Os indicadores socioeconômicos são baseados em dados do **Censo 2010 / Atlas do Desenvolvimento Humano**. A visualização geoespacial utiliza a **Malha Municipal 2023 do IBGE** apenas para representar os limites municipais.

### Variáveis

**Saneamento**
- população com acesso à água encanada;
- população vivendo em domicílios com banheiro e água encanada;
- população urbana com acesso à coleta de lixo.

**Educação**
- subíndice de frequência escolar do IDHM;
- subíndice de escolaridade do IDHM;
- percentual de estudantes de 6 a 14 anos com dois ou mais anos de atraso idade-série.

Como análise complementar, foi incorporada uma variável de renda — renda per capita média do quarto quinto mais pobre — para contextualizar diferenças socioeconômicas entre os clusters.

## Metodologia

1. **Preparação dos dados** — limpeza, conversão de tipos, transformação de percentuais e remoção de observações incompletas com Pandas.
2. **Padronização das variáveis** — normalização por Z-score com `StandardScaler`, do Scikit-learn.
3. **Avaliação do número de clusters** — utilização do **Método da Silhueta** e do **Método do Cotovelo**.
4. **Clusterização** — aplicação do **K-Means** com três clusters.
5. **Interpretação estatística** — análise de correlação de Pearson e comparação dos indicadores por cluster.
6. **Visualização** — boxplots, relações entre variáveis e resumos regionais com Matplotlib e Seaborn.
7. **Integração geoespacial** — associação dos rótulos dos clusters à malha municipal brasileira e análise no QGIS.
8. **Contextualização socioeconômica** — comparação com indicador de renda para observar sobreposição de vulnerabilidades.

## Principais Resultados

Os 5.556 municípios foram agrupados em três perfis analíticos:

| Cluster | Municípios | Perfil geral |
| --- | ---: | --- |
| **0** | 2.018 | Condições intermediárias de saneamento e educação, com maior variabilidade. |
| **1** | 860 | Perfil de maior vulnerabilidade, combinando infraestrutura sanitária mais precária e piores indicadores educacionais. |
| **2** | 2.678 | Perfil mais favorável, com melhor acesso a saneamento, frequência escolar e indicadores educacionais. |

### Padrão regional

- **Cluster 0** apresenta maior presença no Nordeste.
- **Cluster 1** aparece com maior força na região Norte.
- **Cluster 2** é fortemente representado no Sul e Sudeste.

Esses padrões evidenciam como desigualdades de infraestrutura e educação se sobrepõem territorialmente no Brasil.

### Principais achados analíticos

- Municípios com melhor infraestrutura de saneamento tenderam a apresentar melhores indicadores educacionais.
- O Cluster 2 apresentou maior acesso à água encanada e coleta de lixo, melhores indicadores de frequência/escolaridade e menor atraso idade-série.
- O Cluster 1 concentrou os piores indicadores de saneamento e educação.
- Frequência escolar e atraso idade-série apresentaram forte associação negativa: menor frequência coincidiu com maior atraso.
- A análise complementar de renda reforçou o padrão geral: municípios de maior renda tenderam a apresentar melhores condições de saneamento e educação.

## Resultado Geoespacial

![Clusters municipais no Brasil](imagens/mapa_clusters.png)

Os artefatos geoespaciais estão disponíveis em `data/geospacial/`, incluindo o projeto do QGIS e os arquivos componentes do shapefile gerado.

## Interpretação

Este projeto deve ser entendido como uma **análise exploratória e associativa**. K-Means e correlação de Pearson permitem identificar estruturas e relações nos dados observados, mas **não estabelecem relações causais** entre saneamento e desempenho educacional.

Os clusters podem apoiar interpretação territorial e priorização, mas não devem ser tratados como classificações definitivas ou recomendações diretas de política pública.

## Limitações

- Os indicadores socioeconômicos são baseados em **dados de 2010**.
- Os resultados dependem da seleção de variáveis, do escalonamento e da escolha do número de clusters.
- O K-Means assume uma estrutura de agrupamento baseada em distância e pode não capturar todos os padrões socioeconômicos existentes.
- A análise identifica associação, não causalidade.

Entre as extensões propostas no próprio trabalho estão o uso de dados censitários mais recentes, inclusão de variáveis como saúde, emprego e acesso à tecnologia, métodos de machine learning mais avançados e simulações preditivas de cenários de políticas públicas integradas.

## Tecnologias

| Área | Ferramentas |
| --- | --- |
| Análise de dados | Python, Pandas |
| Machine Learning | scikit-learn, K-Means |
| Análise estatística | Correlação de Pearson |
| Visualização | Matplotlib, Seaborn |
| Análise geoespacial | QGIS, Shapefile |
| Ambiente de desenvolvimento | Jupyter Notebook |

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
├── CITATION.md
├── LICENSE
├── README.MD
├── README_PTBR.md
└── requirements.txt
```

## Como Reproduzir

```bash
git clone https://github.com/limapablo/kmeans-saneamento-educacao.git
cd kmeans-saneamento-educacao
python -m venv .venv
pip install -r requirements.txt
jupyter notebook notebook/kmeans_saneamento_educacao.ipynb
```

Para a parte espacial, abra `data/geospacial/mapa_clusters.qgz` no QGIS.

> Este repositório preserva os artefatos analíticos produzidos no estudo acadêmico. A reprodução exata pode depender das versões das bibliotecas e da estrutura das bases públicas disponíveis à época da pesquisa.

## Contexto Acadêmico e Publicação

Este projeto teve origem no **TCC do MBA em Data Science & Analytics da USP/ESALQ** e posteriormente se tornou um artigo científico assinado por **Pablo Henrique da Silva Lima** e **Miguel Ângelo Lellis Moreira**.

- **Artigo:** *Saneamento e Educação: Explorando Padrões em Municípios Brasileiros através de Clusterização*
- **Evento:** XIII Simpósio de Engenharia de Produção — SIMEP, 2025
- **DOI:** [10.29327/23189258.1068040](https://doi.org/10.29327/23189258.1068040)
- **Carta de aceite do SIMEP 2025:** [visualizar documento](https://www.even3.com.br/participante/impressao/_impressaocartadeaceite?code=1068040)

## Competências Demonstradas

- análise exploratória e pré-processamento de dados;
- machine learning não supervisionado;
- validação e interpretação de clusters;
- análise estatística de correlação;
- integração geoespacial e análise territorial;
- comunicação de resultados em contexto acadêmico e de políticas públicas;
- atenção a limitações metodológicas e interpretação não causal.

## Autor

**Pablo Henrique da Silva Lima**  
MBA em Data Science & Analytics — USP/ESALQ  
Bacharel em Administração — UFRRJ

- [Portfólio](https://limapablo.com)
- [LinkedIn](https://www.linkedin.com/in/limapablo/)
- [GitHub](https://github.com/limapablo)
- [ORCID](https://orcid.org/0009-0007-6456-6993)

## Como Citar

Se você utilizar os **resultados, metodologia ou conclusões da pesquisa**, cite o artigo publicado. Referências prontas estão disponíveis nos formatos:

- **ABNT**
- **APA 7ª edição**
- **Chicago Author–Date**
- **IEEE**
- **BibTeX**

Veja [`CITATION.md`](CITATION.md) para todos os formatos.

Se você reutilizar especificamente o **código, notebook ou artefatos do repositório**, o GitHub também pode gerar uma citação de software a partir do arquivo [`CITATION.cff`](CITATION.cff).

## Licença

Este repositório é distribuído sob a [Licença MIT](LICENSE). Dados provenientes de instituições públicas externas permanecem sujeitos às condições de uso e atribuição das respectivas fontes.
