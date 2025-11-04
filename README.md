

# DustCast

**DustCast** is a machine learning–driven forecasting system designed to predict **sand and dust storms (SDS)** across the Arabian Peninsula on a **monthly timescale**. By integrating multiple environmental, climate, and satellite-based datasets into a unified modeling framework, DustCast aims to improve early-warning systems and inform decision-making for communities, infrastructure, and security operations affected by dust hazards.

---

## 🌍 Project Overview

Dust storms are among the most significant environmental hazards in arid regions, impacting **air quality, transportation, public health, military operations, and renewable energy production**. Traditional physics-based climate models struggle with localized and rapid variability in dust lifting and transport. DustCast addresses this gap by combining **reanalysis, remote sensing, and teleconnection data** with **machine learning ensemble methods** to provide more explainable and data-driven predictions.

---

## 📊 Key Features

* **Data Integration:** Combines ERA5 reanalysis, MERRA-2 aerosol optical depth,  and Indian Ocean Dipole (IOD) teleconnection indices.
* **Spatio-Temporal Scaling:** Uses the **H3 geospatial indexing system** (resolution 4) for consistent gridding and spatial analysis.
* **Machine Learning Forecasting:** Employs a **Random Forest model** with monthly lagged predictors to forecast dust storm conditions.
* **Climate Change Sensitivity:** Evaluates how changes in land cover, climate teleconnections, and meteorological extremes influence dust storm trends.
* **Data Schema Standardization:** Harmonized schema across datasets:


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

   * MLR, KNN, DT, RF algorithm
   * Predictors: WX variables, AOD, teleconnections
   * Target: Dust storm frequency/intensity

4. **Evaluation**

   * Training/Validaiton period: 1980–2000, 2013-2022
   * Testing: 2023
   * Metrics: RMSE

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

   git clone https://github.com/<your-username>/dustcast.git
   cd dustcast
  
2. Set up the environment:

3. Preprocess datasets:
  
4. Train the model:
 
5. Generate forecasts:

---

## 📈 Outputs

* **Forecast Maps:** Predicted dust storm probabilities aggregated to H3 resolution.
* **Feature Importance:** Ranking of meteorological and teleconnection driving forecasts.
* **Time-Series Analysis:** Dust storm trend comparisons across decades.

---

## 🔮 Applications

* **Environmental Security** – Support for regional partners.
* **Public Health** – Anticipating air quality impacts.
* **Infrastructure & Transport** – Informing aviation, shipping, and logistics planning.
* **Climate Research** – Linking SDS to climate variability.

---

## 📜 Citation

If you use DustCast in your research, please cite:
*Ramos, C. (2025). DustCast: A Machine Learning Framework for Forecasting Sand and Dust Storms Across the Arabian Peninsula. Pennsylvania State University.*

---

## 📧 Contact

**Author:** Christopher Ramos
**Role:** Data Scientist
**Email:** Charlee.romeo23@gmail.com
