🌊 Flood Risk Classification Using Spatial Data & Machine Learning

Case Study: Sumatra, Indonesia

📌 Project Overview

This project aims to perform flood risk classification by integrating spatial raster data, vector data, and non-spatial historical records using Machine Learning. The analysis focuses on administrative-level flood risk (kabupaten) to ensure computational efficiency and meaningful spatial interpretation.

The project is developed as part of a Spatial Programming & Artificial Intelligence assignment, utilizing open-source datasets and Python-based spatial analysis.

🎯 Objectives

Integrate multi-source spatial and non-spatial open datasets

Extract meaningful spatial features using zonal statistics

Apply supervised Machine Learning for flood risk classification

Visualize results using interactive Folium maps

Avoid memory overflow issues through optimized spatial aggregation

🗂️ Data Sources

All datasets used in this project are open-source and publicly available.

📍 Spatial Data
Dataset	Description	Format	Source
Sentinel-1 Flood Inundation (ACD)	Flood extent raster	GeoTIFF	Copernicus
DEM	Elevation data	GeoTIFF	Open DEM
WorldPop	Population density	GeoTIFF	WorldPop
Administrative Boundary	Kabupaten boundaries	Shapefile	BPS / BIG
River Network	River vector data	Shapefile	OpenStreetMap
📊 Non-Spatial Data
Dataset	Description	Format	Source
Flood Events per Kabupaten	Historical flood records	CSV	BNPB (Data Bencana Indonesia)
🧠 Methodology
1️⃣ Data Preprocessing

All datasets are harmonized to EPSG:4326

Raster datasets are processed using zonal statistics

NoData handling is explicitly defined to avoid overflow errors

2️⃣ Feature Engineering

Extracted features per kabupaten:

Mean flood inundation value (Sentinel-1)

Mean elevation (DEM)

Total population (WorldPop)

Mean distance to nearest river

Historical flood frequency (BNPB)

3️⃣ Target Variable

Flood risk classes are defined based on historical flood frequency:

0 → Low Risk

1 → High Risk

Threshold is determined empirically and justified in the methodology.

4️⃣ Machine Learning

Algorithm: Random Forest Classifier

Train-test split: 70% / 30%

Features scaled implicitly through tree-based modeling

5️⃣ Model Evaluation

Evaluation metrics include:

Accuracy

Precision

Recall

F1-score

Confusion Matrix

Feature Importance Analysis

6️⃣ Visualization

Interactive choropleth map using Folium

Flood risk prediction visualized per kabupaten

📈 Results

The model successfully classifies flood risk with robust performance metrics.
Feature importance analysis highlights:

Distance to river

Flood inundation intensity

Elevation

as dominant contributing factors to flood risk.

🗺️ Visualization Example

The final output is an interactive web map displaying predicted flood risk levels per kabupaten.

Yellow–Red color gradient represents increasing flood risk.

⚙️ Technical Notes

Raster processing is performed at administrative unit level to prevent memory overflow (OOM)

zonal_stats uses explicit nodata handling for unsigned integer rasters

EPSG:4326 is used to ensure full regional coverage across Sumatra

🧪 How to Run

Clone the repository:

git clone https://github.com/your-username/flood-risk-ml.git


Open the notebook in Google Colab or Jupyter:

Flood_Risk_Admin_ML_Folium.ipynb


Mount Google Drive and update file paths if necessary

Run cells sequentially

📦 Dependencies
geopandas
rasterio
rasterstats
scikit-learn
folium
pandas
numpy
matplotlib
seaborn

📚 References

BNPB – Data Bencana Indonesia

Copernicus Sentinel-1

WorldPop

OpenStreetMap

Scikit-learn Documentation

👤 Author

Anindya R Putri Alindita
Bachelor Student – Geodesy Engineering
Spatial Data Science | GIS | Remote Sensing | AI

📜 License

This project is intended for academic and educational purposes.
