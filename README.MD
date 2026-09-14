# Municipal Sanitation & Education Clustering in Brazil

[![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-K--Means-F7931E?logo=scikitlearn&logoColor=white)](https://scikit-learn.org/)
[![QGIS](https://img.shields.io/badge/QGIS-Geospatial%20Analysis-589632?logo=qgis&logoColor=white)](https://qgis.org/)
[![DOI](https://img.shields.io/badge/DOI-10.29327%2F23189258.1068040-blue)](https://doi.org/10.29327/23189258.1068040)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

> An applied data science study using **K-Means clustering** and geospatial analysis to identify patterns across Brazilian municipalities based on sanitation and education indicators.

**Academic origin:** this repository was developed from my **MBA in Data Science & Analytics capstone project (TCC) at USP/ESALQ**. The study was subsequently developed into a **scientific paper published from the project**, with DOI **[10.29327/23189258.1068040](https://doi.org/10.29327/23189258.1068040)**, associated with SIMEP 2025.

[Leia em Português](README_PTBR.md)

---

## Project Overview

Public-policy analysis often requires comparing municipalities with very different infrastructure and socioeconomic profiles. This project explores whether unsupervised machine learning can organize part of that complexity into interpretable groups.

The analysis applies **K-Means clustering** to municipal-level indicators related to basic sanitation and education, then connects the resulting clusters to Brazil's municipal geographic boundaries for spatial interpretation.

### Research question

> Can Brazilian municipalities be grouped into meaningful profiles based on sanitation and educational indicators in a way that supports more targeted public-policy analysis?

## Objectives

- Identify groups of municipalities with similar sanitation and education profiles.
- Apply an end-to-end unsupervised machine-learning workflow to public data.
- Interpret the resulting clusters in a real socioeconomic context.
- Visualize the geographic distribution of the clusters across Brazil.
- Demonstrate how data science can support exploratory public-policy and territorial analysis.

## Methodology

The project follows an end-to-end analytical workflow:

1. **Data acquisition** — municipal indicators obtained from public datasets.
2. **Data preparation** — cleaning, integration, variable selection and preprocessing.
3. **Feature scaling** — normalization before distance-based clustering.
4. **Clustering** — application of the K-Means algorithm.
5. **Cluster interpretation** — comparison of municipality profiles across sanitation and education indicators.
6. **Geospatial integration** — association of cluster labels with official municipal boundaries.
7. **Spatial visualization** — mapping and regional interpretation in QGIS.

## Tech Stack

| Area | Tools |
| --- | --- |
| Data analysis | Python, Pandas |
| Machine learning | scikit-learn, K-Means |
| Visualization | Matplotlib, Seaborn |
| Geospatial analysis | QGIS, Shapefile |
| Development environment | Jupyter Notebook |

## Geospatial Output

The cluster labels were joined to official Brazilian municipal geometries, producing a geospatial layer that can be explored in QGIS or another GIS tool.

![Municipal clusters across Brazil](imagens/mapa_clusters.png)

The geospatial deliverables are available in `data/geospacial/` and include the QGIS project plus the component files of the generated municipal shapefile.

The municipal boundaries used in the study were based on the **IBGE 2023 Municipal Mesh**.

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
├── LICENSE
├── README.MD
├── README_PTBR.md
└── requirements.txt
```

## Reproducing the Analysis

Clone the repository and create a Python environment:

```bash
git clone https://github.com/limapablo/kmeans-saneamento-educacao.git
cd kmeans-saneamento-educacao
python -m venv .venv
```

Activate the environment and install the dependencies:

```bash
pip install -r requirements.txt
```

Then open the notebook:

```bash
jupyter notebook notebook/kmeans_saneamento_educacao.ipynb
```

For the spatial component, open `data/geospacial/mapa_clusters.qgz` in QGIS.

> This repository preserves the analytical artifacts produced for the academic study. Exact reproducibility may depend on software versions and on the structure of the source datasets available at the time of the research.

## Academic Context & Publication

This project originated as the **final capstone project (TCC)** of the MBA in Data Science & Analytics at **USP/ESALQ**.

The work later evolved into a scientific article associated with **SIMEP 2025 — Simpósio de Engenharia de Produção**.

- **Article DOI:** [10.29327/23189258.1068040](https://doi.org/10.29327/23189258.1068040)
- **SIMEP 2025 acceptance letter:** [view document](https://www.even3.com.br/participante/impressao/_impressaocartadeaceite?code=1068040)

This repository therefore serves both as a **technical portfolio project** and as the **computational record of an academic research project**.

## What This Project Demonstrates

From a portfolio perspective, the project demonstrates experience with:

- exploratory data analysis and preprocessing;
- unsupervised machine learning;
- feature scaling and clustering workflows;
- interpretation of model outputs in a real-world context;
- integration of tabular and geospatial data;
- communication of analytical results through maps and visualizations;
- application of data science to public-sector and socioeconomic questions.

## Limitations

K-Means is an exploratory clustering technique and does not establish causal relationships between sanitation and educational outcomes. Results are also sensitive to feature selection, scaling choices and the selected number of clusters.

The clusters should therefore be interpreted as **analytical profiles**, not as definitive classifications or direct policy prescriptions.

## Author

**Pablo Henrique da Silva Lima**  
MBA in Data Science & Analytics — USP/ESALQ  
B.Sc. in Business Administration — UFRRJ

- [LinkedIn](https://www.linkedin.com/in/limapablo/)
- [GitHub](https://github.com/limapablo)

## Citation

If this repository is useful in academic work, please cite the associated article using DOI **10.29327/23189258.1068040** and/or use the repository citation metadata available in [`CITATION.cff`](CITATION.cff).

## License

This repository is distributed under the [MIT License](LICENSE). Data originating from external public institutions remains subject to the terms and attribution requirements of the respective source providers.
