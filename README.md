## README: Comprehensive School Risk Mapping System

---

### Overview

This tool is a **Comprehensive Risk Mapping System** designed to enhance UNICEF's Children's Climate and Environmental Risk Index (CCRI) by integrating local, school-level data to a generalized framework for analyzing risks to schoolchildren that supplements and extends with fine-grained,
location-specific data analysis. 

## 📊 Project Presentation

To understand the full context, data pipeline, and visual approach behind this tool, check out our interactive presentation:

👉 [Enhancing Child-Centered Climate Risk Tools](https://gamma.app/docs/Enhancing-Child-Centered-Climate-Risk-Tools-5hx0mkkoqc8mjtm)


---

### Key Capabilities

* Supports geospatial and tabular data for **any country**.
* Produces **composite risk scores** for each school based on:

  * Works with any country's data input
  * Healthcare accessibility analysis
  * Road condition assessment
  * Infrastructure age evaluation
  * Proximity to "shelter base"
  * Composite risk scoring with map overlays
  * Comprehensive labeling and visualization
* Provides visualizations for maps, graphs, and dashboards.
* Exports in multiple formats: CSV, GeoJSON, Excel.

---

### Data Inputs (required)

Currently tly the trial has been using data from Tajikistan; however, the code can be replicated and implemented in other countries 

Place files inside a `data/` directory:

* **Healthcare facilities**: e.g., `healthcare_tajikistan.csv`
* **Education facilities**: e.g., `hotosm_tjk_education_facilities_points_geojson.geojson`
* **Road infrastructure (optional)**

---

### Configuration

Customizable weights and parameters (see `tajikistan_config` in script):

* `risk_weights`: adjusts relative importance (e.g., "sheleter space" vs. roads)
* `distance_thresholds`: defines what counts as emergency/routine access
* `facility_priorities`: weights for different healthcare types
* `infrastructure_age_indicators`: keywords for building age estimation

---

### Usage

Run the script via:

```bash
python3 school_risk_mapper.py
```

The default example runs an analysis for Tajikistan using sample files and saves all outputs to the folder:

```
tajikistan_comprehensive_analysis/
```

---

### Outputs

* `*_comprehensive_risk_map.png`: Static overview map
* `*_interactive_risk_map.html`: Folium-based interactive map
* `*_healthcare_analysis.png`: Visual summaries of access
* `*.geojson`, `*.csv`, `*.xlsx`: Risk results with metadata
* `*_report.txt`, `*_summary.json`: Exported risk summaries

---

### Notable Features

* Auto-detection of coordinate columns in CSVs
* Risk scoring logic includes clustering and proxies for terrain
* Naming conventions of schools help infer infrastructure quality
* Environmental risk uses basic proxies; can be improved with more data

---

### Recommended Improvements

* Integrate **real DEM/elevation and climate hazard datasets**
* Add functionality to ingest **population vulnerability layers**
* Extend road condition module using **OpenStreetMap** tags
* Include modules for **budget allocation modeling**

---

### Requirements

Python 3.x with the following packages:

* `pandas`, `geopandas`, `numpy`, `matplotlib`, `seaborn`, `folium`, `plotly`, `scikit-learn`, `contextily`, `openpyxl`

Install via:

```bash
pip install -r requirements.txt
```

---

### Authors

Adapted and expanded from the UN-Tech-Over challenge framework

For more, see: [https://opensource.unicc.org/open-source-united-initiative/un-tech-over/](https://opensource.unicc.org/open-source-united-initiative/un-tech-over/)

---

### Integration

The tool's output is compatible with:

* **UNICEF GeoSight**
* **GigaSpatial Python library**
* **OpenStreetMap**-based visual pipelines

---

For questions or enhancements, contact the script maintainer or contribute via pull request.
