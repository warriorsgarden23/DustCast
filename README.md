# DustCast

**DustCast** is a machine learning–driven forecasting system designed to predict **sand and dust storms (SDS)** across the Arabian Peninsula on a **monthly timescale**. By integrating multiple environmental, climate, and satellite-based datasets into a unified modeling framework, DustCast aims to improve early-warning systems and inform decision-making for communities, infrastructure, and security operations affected by dust hazards.

---

## 🌍 Project Overview

Dust storms are among the most significant environmental hazards in arid regions, impacting **air quality, transportation, public health, military operations, and renewable energy production**. Traditional physics-based climate models struggle with localized and rapid variability in dust lifting and transport. DustCast addresses this gap by combining **reanalysis, remote sensing, and teleconnection data** with **machine learning ensemble methods** to provide more explainable and data-driven predictions.

---

## 📊 Key Features

* **Data Integration:** Combines ERA5 reanalysis, MERRA-2 aerosol optical depth, Sentinel-2 land use/land cover, and Indian Ocean Dipole (IOD) teleconnection indices.
* **Spatio-Temporal Scaling:** Uses the **H3 geospatial indexing system** (resolution 6) for consistent gridding and spatial analysis.
* **Machine Learning Forecasting:** Employs a **Random Forest model** with monthly lagged predictors to forecast dust storm conditions.
* **Climate Change Sensitivity:** Evaluates how changes in land cover, climate teleconnections, and meteorological extremes influence dust storm trends.
* **Data Schema Standardization:** Harmonized schema across datasets:

  ```
  Time (TIMESTAMPZ)
  Latitude (Float)
  Longitude (Float)
  H3_Index (Int64)
  Level (Int64)
  WX_Variables (Float)
  Merra2_Variables (Float)
  Land_Cover_Code (Int8)
  ```

---

## 📂 Dataset Sources

* **ERA5 Reanalysis (1980–2023)** – Meteorological reanalysis variables.
* **MERRA-2 Aerosol Optical Depth (1980–2023)** – Aerosol assimilation data.
* **IOD Teleconnection Index (1800s–2023)** – Climate oscillation indicator.

All datasets are preprocessed into **Parquet** files for efficient storage and analysis.

---

## 🛠️ Technical Workflow

1. **Data Download & Preprocessing**

   * ERA5 (hourly → monthly aggregation)
   * MERRA-2 (AOD hourly → monthly)
   * Teleconnection indices alignment

2. **Feature Engineering**

   * Monthly max, min, and averages
   * Spatial join with H3 indexing
   * Schema alignment

3. **Modeling**

   * Multiple Linear Regression, K-Nearest Neighbor, Decision Tree, Random Forest algorithm
   * Predictors: WX variables, AOD, teleconnections
   * Target: Dust storm frequency/intensity at monthly temporal scale

4. **Evaluation**

   * Training period: 1980-2000, 2013-2022
   * Testing/validation: 2023
   * Metrics: RMSE, MSE, MAE, Feature Importance, Anomaly, Bias

---

## 🚀 Getting Started

### Prerequisites

* Python 3.9+
* Conda or venv environment
* Recommended libraries:

  ```bash
  pip install pandas numpy geopandas scikit-learn h3-py pyarrow matplotlib xarray
  ```

### Running the Project

1. Clone the repository:

2. Set up the environment:

3. Preprocess datasets:

4. Train the model:

5. Generate forecasts:


---

## 📈 Outputs

* **Forecast Maps:** Predicted dust storm probabilities aggregated to H3 resolution.
* **Feature Importance:** Ranking of meteorological, teleconnection, and land cover variables driving forecasts.
* **Time-Series Analysis:** Dust storm trend comparisons across decades.

---

## 🔮 Applications

* **Environmental Security** – Support for regional partners.
* **Public Health** – Anticipating air quality impacts.
* **Infrastructure & Transport** – Informing aviation, shipping, and logistics planning.
* **Climate Research** – Linking SDS to climate variability and anthropogenic land-use changes.

---

## 📜 Citation

If you use DustCast in your research, please cite:
*Ramos, C. (2025) DustCast: An ensemble machine learning model for monthly atmospheric dust aerosol forecasting across the Arabian Peninsula (Master’s Thesis, Pennsylvania State University, Spatial Data Science).
---

## 📧 Contact

**Author:** Chris Ramos
**Role:** Principal Data Scientist, Warriors Garden Solutions
**Email:** warriorsgardensolutions@gmail.com

---
