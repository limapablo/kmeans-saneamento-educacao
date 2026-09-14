# Municipal Sanitation & Education Clustering in Brazil

[![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-K--Means-F7931E?logo=scikitlearn&logoColor=white)](https://scikit-learn.org/)
[![QGIS](https://img.shields.io/badge/QGIS-Geospatial%20Analysis-589632?logo=qgis&logoColor=white)](https://qgis.org/)
[![DOI](https://img.shields.io/badge/DOI-10.29327%2F23189258.1068040-blue)](https://doi.org/10.29327/23189258.1068040)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

> Applied data science research using **K-Means clustering, correlation analysis and geospatial interpretation** to identify sanitation and education patterns across Brazilian municipalities.

**Academic origin:** this repository was developed from my **MBA in Data Science & Analytics capstone project (TCC) at USP/ESALQ**. The work later evolved into the scientific paper **“Saneamento e Educação: Explorando Padrões em Municípios Brasileiros através de Clusterização”**, presented at the XIII Simpósio de Engenharia de Produção (SIMEP) in 2025.

**Published paper:** [10.29327/23189258.1068040](https://doi.org/10.29327/23189258.1068040)  
**Portfolio case study:** [limapablo.com/projects/sanitation-education-clustering/](https://limapablo.com/projects/sanitation-education-clustering/)  
[Leia em Português](README_PTBR.md)

---

## Research Question

> Can Brazilian municipalities be grouped into meaningful profiles based on sanitation and education indicators in a way that helps reveal territorial inequalities and support more targeted public-policy analysis?

## Dataset & Scope

The analytical sample contains **5,556 Brazilian municipalities** after removing observations with missing data.

The socioeconomic indicators are based on **IBGE Census 2010 / Atlas do Desenvolvimento Humano** data. The geospatial visualization uses the **IBGE 2023 Municipal Mesh** only for municipal boundaries.

### Variables

**Sanitation**
- population with access to piped water;
- population living in households with a bathroom and piped water;
- urban population with access to waste collection.

**Education**
- IDHM school-attendance subindex;
- IDHM educational-attainment subindex;
- percentage of students aged 6–14 with two or more years of age-grade delay.

A complementary income variable — the average per-capita income of the fourth poorest quintile — was later incorporated to contextualize socioeconomic differences between clusters.

## Methodology

1. **Data preparation** — cleaning, type conversion, percentage transformation and removal of incomplete observations with Pandas.
2. **Feature standardization** — Z-score scaling with Scikit-learn's `StandardScaler`.
3. **Cluster-number assessment** — evaluation using the **Silhouette Method** and **Elbow Method**.
4. **Clustering** — application of **K-Means** with three clusters.
5. **Statistical interpretation** — Pearson correlation analysis and cluster-level comparison of indicators.
6. **Visualization** — boxplots, pairwise relationships and regional summaries with Matplotlib and Seaborn.
7. **Geospatial integration** — cluster labels joined to Brazilian municipal boundaries and mapped in QGIS.
8. **Socioeconomic context** — comparison with an income indicator to examine overlapping vulnerability patterns.

## Main Results

The 5,556 municipalities were grouped into three analytical profiles:

| Cluster | Municipalities | General profile |
| --- | ---: | --- |
| **0** | 2,018 | Intermediate sanitation and education conditions, with greater variability. |
| **1** | 860 | Most vulnerable profile, combining weaker sanitation infrastructure and poorer educational indicators. |
| **2** | 2,678 | Strongest profile, with better sanitation access, school attendance and educational outcomes. |

### Regional pattern

- **Cluster 0** is more prevalent in the Northeast.
- **Cluster 1** is more prevalent in the North.
- **Cluster 2** is strongly represented in the South and Southeast.

These patterns highlight how infrastructure and education inequalities overlap geographically across Brazil.

### Key analytical findings

- Municipalities with stronger sanitation infrastructure tended to also show better educational indicators.
- Cluster 2 showed higher access to piped water and waste collection, higher school-attendance and educational-attainment indicators, and lower age-grade delay.
- Cluster 1 concentrated the weakest sanitation and educational conditions.
- School attendance and age-grade delay showed a strong negative association: lower attendance coincided with higher delay.
- The complementary income analysis reinforced the broader pattern: municipalities with higher income tended to show stronger sanitation and education indicators.

## Geospatial Output

![Municipal clusters across Brazil](imagens/mapa_clusters.png)

The geospatial deliverables are available in `data/geospacial/` and include the QGIS project plus the component files of the generated municipal shapefile.

## Interpretation

This project is best understood as **exploratory and associative analysis**. K-Means and Pearson correlation reveal structure and relationships in the observed data, but they do **not establish causal effects** between sanitation and educational outcomes.

The clusters can support territorial interpretation and prioritization, but they should not be treated as definitive classifications or direct policy prescriptions.

## Limitations

- The socioeconomic indicators are based on **2010 data**.
- Results depend on the selected variables, scaling procedure and choice of `k`.
- K-Means assumes a distance-based cluster structure and may not capture every socioeconomic pattern.
- The analysis identifies association, not causation.

Future extensions proposed in the research include newer census data, additional variables such as health, employment and technology access, more advanced machine-learning approaches and predictive simulations of integrated public-policy scenarios.

## Tech Stack

| Area | Tools |
| --- | --- |
| Data analysis | Python, Pandas |
| Machine learning | scikit-learn, K-Means |
| Statistical analysis | Pearson correlation |
| Visualization | Matplotlib, Seaborn |
| Geospatial analysis | QGIS, Shapefile |
| Development environment | Jupyter Notebook |

## Repository Structure

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

## Reproducing the Analysis

```bash
git clone https://github.com/limapablo/kmeans-saneamento-educacao.git
cd kmeans-saneamento-educacao
python -m venv .venv
pip install -r requirements.txt
jupyter notebook notebook/kmeans_saneamento_educacao.ipynb
```

For the spatial component, open `data/geospacial/mapa_clusters.qgz` in QGIS.

> This repository preserves the analytical artifacts produced for the academic study. Exact reproducibility may depend on software versions and on the structure of the source datasets available at the time of the research.

## Academic Context & Publication

This project originated as the **final capstone project (TCC)** of the MBA in Data Science & Analytics at **USP/ESALQ** and later became a scientific paper authored by **Pablo Henrique da Silva Lima** and **Miguel Ângelo Lellis Moreira**.

- **Paper:** *Saneamento e Educação: Explorando Padrões em Municípios Brasileiros através de Clusterização*
- **Event:** XIII Simpósio de Engenharia de Produção — SIMEP, 2025
- **DOI:** [10.29327/23189258.1068040](https://doi.org/10.29327/23189258.1068040)
- **SIMEP 2025 acceptance letter:** [view document](https://www.even3.com.br/participante/impressao/_impressaocartadeaceite?code=1068040)

## What This Project Demonstrates

- exploratory data analysis and preprocessing;
- unsupervised machine learning;
- cluster validation and interpretation;
- statistical correlation analysis;
- geospatial integration and territorial analysis;
- communication of model results in academic and public-policy contexts;
- awareness of methodological limitations and non-causal interpretation.

## Author

**Pablo Henrique da Silva Lima**  
MBA in Data Science & Analytics — USP/ESALQ  
B.Sc. in Business Administration — UFRRJ

- [Portfolio](https://limapablo.com)
- [LinkedIn](https://www.linkedin.com/in/limapablo/)
- [GitHub](https://github.com/limapablo)
- [ORCID](https://orcid.org/0009-0007-6456-6993)

## How to Cite

If you use the **research findings, methodology or results**, cite the published paper. Ready-to-use references are available in:

- **ABNT**
- **APA 7th edition**
- **Chicago Author–Date**
- **IEEE**
- **BibTeX**

See [`CITATION.md`](CITATION.md) for all formats.

If you specifically reuse the **code, notebook or repository artifacts**, GitHub can also generate a software citation from [`CITATION.cff`](CITATION.cff).

## License

This repository is distributed under the [MIT License](LICENSE). Data originating from external public institutions remains subject to the terms and attribution requirements of the respective source providers.
