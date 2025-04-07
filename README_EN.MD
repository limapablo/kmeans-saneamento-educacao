# 🧠 K-Means for Decision Making in Sanitation and Education

This project applies clustering techniques (K-Means) to Brazilian municipal data, focusing on basic sanitation access and educational performance indicators. The goal is to propose a data-driven model to support the prioritization of public policies.

## 🔍 Problem

How can we identify groups of municipalities with similar characteristics in terms of infrastructure and educational performance to support more effective public decision-making?

## 📊 Approach

1. **Data Collection**: public data sources (IBGE).
2. **Preprocessing**: cleaning, normalization, and variable selection.
3. **Modeling**: application of the K-Means algorithm.
4. **Cluster Analysis**: interpretation of the formed groups.
5. **Visualization**: charts and maps to support insights.

## 🧪 Technologies and Tools

- Python
- Pandas
- Scikit-learn
- Seaborn / Matplotlib
- Jupyter Notebook
- QGIS (for geospatial visualization)

## 🌎 Geospatial Visualization

The clustering results were visualized using **QGIS**, an open-source software for geospatial analysis. A map of Brazilian municipalities was created, highlighting the clusters formed by the model, enabling regional interpretation of the patterns found.

### 📍 Geospatial Data

To generate the map with clustered municipalities, official **Shapefiles** of Brazilian municipalities were used and integrated with the K-Means results.

These files are available in the `data/geoespacial/` folder and can be used with **QGIS** or other GIS tools.

📂 `data/geoespacial/`  

- `municipios_com_clusters.shp` — shapefile with cluster labels  
- `mapa_clusters.qgz` — QGIS project file with the final map

🔗 Shapefile source: [IBGE - Municipal Mesh 2023](https://geoftp.ibge.gov.br/organizacao_do_territorio/malhas_territoriais/malhas_municipais/municipio_2023/Brasil/BR_Municipios_2023.zip)

## 📁 Repository Structure
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

## 📈 Expected Outcomes

- Municipal clusters with similar infrastructure and education profiles.
- A data-driven basis for public policy planning.

## 📄 Additional Documentation

This project is based on the Capstone Project of the MBA in Data Science & Analytics (USP/ESALQ) and a paper accepted for publication at the Simpósio de Engenharia de Produção (SIMEP 2025).

📌 [`TCC_MBA_DataScience_USP_ESALQ_PabloLima.pdf`](documentacao/TCC_MBA_DataScience_USP_ESALQ_PabloLima.pdf)  
📌 [`Paper_SIMEP2025_KMeans_Sanitation_Education.pdf`](documentacao/Artigo_SIMEP2025_KMeans_Saneamento_Educacao.pdf) *(to be officially published in May 2025)*  
📌 [`Acceptance Letter - SIMEP 2025`](https://www.even3.com.br/participante/impressao/_impressaocartadeaceite?code=1068040)

## 👤 Author

**Pablo Henrique da Silva Lima**  
MBA in Data Science & Analytics - USP/ESALQ  
Bachelor in Business Administration - UFRRJ

---


🗓️ Paper accepted for publication at SIMEP 2025 ✨
