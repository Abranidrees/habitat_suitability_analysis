# 🏞️ Habitat Site Suitability Analysis — Western Australia

### Geospatial Analysis for the Assessment of Habitat Site Suitability  


---

## 📘 Overview
This project evaluates **habitat site suitability** across three electoral districts in **Western Australia** — **Dawesville, Mandurah, and Murray-Wellington** — using a **GIS-based Multi-Criteria Decision Analysis (MCDA)** approach combined with the **Analytical Hierarchy Process (AHP)**.

The analysis integrates environmental, topographic, and anthropogenic parameters to map regions ranging from *very low* to *very high* suitability for biodiversity conservation and sustainable land management.

---

## 🧭 Objectives
- Identify and map areas suitable for wildlife habitat conservation.  
- Integrate environmental, topographic, and human-influence parameters within a GIS framework.  
- Apply **AHP-based weighting** under the **MCDA** approach for decision-making.  
- Support **biodiversity conservation (SDG 15)** and sustainable land-use planning.

---

## 🗺️ Study Area
The study covers three electoral boundaries — **Dawesville**, **Mandurah**, and **Murray-Wellington** — spanning **~4,596 km²**  
(**33.38°S – 32.44°S**, **115.61°E – 116.26°E**).

These areas represent diverse landscapes, from urban zones to forested regions.

!(<img width="598" height="429" alt="image" src="https://github.com/user-attachments/assets/817b0ac7-bc77-4237-a59b-93f68862f1c5" />)  


---

## 🧩 Data Sources and Parameters

| # | Parameter | Description | Source |
|:-:|------------|-------------|--------|
| 1 | Elevation | SRTM DEM (30 m) | [USGS EarthExplorer](https://earthexplorer.usgs.gov/) |
| 2 | Slope | Derived from DEM | USGS |
| 3 | Landcover | ESA Landcover (10 m) | [Google Earth Engine](https://code.earthengine.google.com/) |
| 4 | NDVI | Sentinel-2 (10 m) | GEE |
| 5 | LST | Landsat-8 (30 m) | GEE |
| 6 | Distance from Roads | Euclidean distance layer | [OpenStreetMap](https://download.geofabrik.de/) |
| 7 | Distance from Settlements | ESA Built-up (10 m) | GEE |
| 8 | Distance from Water Bodies | Global Surface Water (30 m) | [EC JRC](https://global-surface-water.appspot.com/) |

All rasters were resampled to **30 m resolution** and reprojected to **GDA 1994 MGA Zone 51**.

---

## ⚙️ Methodology
<img width="671" height="298" alt="image" src="https://github.com/user-attachments/assets/cc8505dc-4b93-47c7-bcee-73aecb98c5c1" />

### 1️⃣ Data Preparation
- Extracted DEM, NDVI, LST, and Landcover from **Google Earth Engine**.  
- Generated slope and Euclidean proximity layers (to roads, settlements, waterbodies) using **ArcGIS Pro**.  
- Reprojected and resampled all rasters to maintain spatial consistency.

### 2️⃣ Analytical Hierarchy Process (AHP)
- Constructed a pairwise comparison matrix for all parameters.  
- Derived weights based on literature and expert knowledge.  
- Verified the **Consistency Ratio (CR = 1.8 %)**.

| Rank | Parameter | Weight |
|------|------------|--------|
| 1 | Landcover | 0.395 |
| 2 | NDVI | 0.214 |
| 3 | Distance from Roads | 0.103 |
| 4 | Distance from Settlements | 0.103 |
| 5 | Distance from Water Bodies | 0.068 |
| 6 | Elevation | 0.039 |
| 7 | Slope | 0.039 |
| 8 | LST | 0.039 |
<img width="653" height="284" alt="image" src="https://github.com/user-attachments/assets/72eb22b6-4589-4d8a-a07d-ab2c41648b10" />

### 3️⃣ Weighted Overlay Analysis (WOA)
- Reclassified each raster into five suitability levels *(1 = Very Low → 5 = Very High)*.  
- Applied weights using ArcGIS Pro’s **Weighted Overlay** tool.  
- Generated the final **Habitat Site Suitability Map**.

---

## 🌍 Results

- Around **45 %** of the total area falls under *High* and *Very High* suitability.  
- **Eastern and southeastern** parts show optimal habitat conditions (dense forest, moderate slopes, low LST).  
- *Low* and *Very Low* areas occur near **urbanized and road-dense** zones.  
- **Landcover** and **NDVI** were the most influential parameters, contributing **~61 %** of total weight.

<img width="617" height="824" alt="image" src="https://github.com/user-attachments/assets/bac00300-972d-41bc-85cf-f1c446407202" />

---

## 📈 Class-wise Area Statistics

| Suitability Class | Area (km²) | Description |
|:------------------|:-----------:|:-------------|
| Very High | 1264.5 | Excellent habitat potential |
| High | 1217.8 | Strong conservation value |
| Moderate | 983.4 | Intermediate conditions |
| Low | 910.7 | Disturbed or altered areas |
| Very Low | 202.8 | Unsuitable regions |

---

## 🧠 Key Insights
- **Forested and vegetated** zones are vital for species diversity and stability.  
- **Human proximity** (roads, settlements) drastically reduces habitat quality.  
- **Moderate slopes** (15°–25°) and **cooler LST** (< 28 °C) enhance habitat suitability.

---

## 🧩 Tools & Technologies
- 🛰️ **Google Earth Engine (GEE)** – NDVI, LST, Landcover extraction  
- 🗺️ **ArcGIS Pro** – Raster processing, Euclidean distance, Weighted Overlay  
- 🧮 **AHP Calculator** – Pairwise comparison and consistency ratio  
- 🐍 **Python / Overpass API** – OSM road network extraction  
- 🌍 **ESA | USGS | JRC** – Data sources

---


