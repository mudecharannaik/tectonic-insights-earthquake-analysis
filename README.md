# 🌍 Tectonic Insights: A Complete Data Analytics Lifecycle on Global Earthquakes

### *A comprehensive end-to-end data analytics project covering Data Quality, Visualization, and Storytellingn using 1M+ global earthquake records.*

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Pandas](https://img.shields.io/badge/Pandas-2.0%2B-green)
![Plotly](https://img.shields.io/badge/Plotly-Interactive-orange)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-lightgrey)

---

## 📖 Project Overview

This project was developed as a **fresher data analyst's portfolio piece** to demonstrate a robust, end-to-end data science workflow. Using the Kaggle **"Global Earthquake History: 1M+ Since 1900"** dataset, I performed a 5-stage analytical lifecycle:

1. **Data Quality Validation** (Handling nulls, duplicates, and intentional outlier preservation).
2. **Documentation & Knowledge** (Creating data dictionaries and assumptions).
3. **Data Analysis & Investigation** (Uncovering temporal, spatial, and depth trends).
4. **Data Storytelling & Visualization** (Building optimized, publication-quality charts).
5. **Stakeholder Communication** (Translating complex data into actionable business insights).


The result is a fully reproducible Jupyter Notebook that handles 1 million rows efficiently, corrects common statistical misinterpretations, and presents a professional executive dashboard.

---

## 🚀 Key Features & Techniques

- **Robust Data Cleaning**: Handled missing values strategically (dropped `dmin`/`nst`/`gap` >50%, imputed `rms`/`magType`, re-derived `depth_category` from imputed depth). Correctly parsed ISO8601 timestamps with microseconds.
- **Scientific Outlier Preservation**: **Crucially** avoided removing magnitude outliers. In seismology, the largest earthquakes (M > 8.0) are not "errors" but the most important physical phenomena.
- **Performance Optimization**: Implemented vectorized pandas operations, random sampling for interactive Plotly charts, and **Hexbin Aggregation** for static maps to prevent browser freezes and memory crashes with 850k+ rows.
- **Statistical Corrections**: Analyzed depth distributions to correctly identify the bimodal peaks at **10 km and 33 km**, explicitly refuting the common error of finding a 100 km peak.
- **Executive Dashboard**: Designed a static, multi-panel Plotly dashboard to summarize the entire analysis for stakeholder presentation.

---

## 🛠️ Tech Stack

| Library | Purpose |
| :--- | :--- |
| **Pandas / NumPy** | Data manipulation, cleaning, and vectorized operations |
| **Matplotlib / Seaborn** | Static publication-quality visualizations |
| **Plotly** | Interactive scatter plots, 2D heatmaps, and executive dashboards |
| **GeoPandas / Shapely** | (Optional) Geographic data handling |

---

## 📂 Dataset Information

- **Source**: [Kaggle - Global Earthquake History: 1M+ Since 1900]([https://www.kaggle.com/datasets/usgs/earthquake-database](https://www.kaggle.com/datasets/darkmatternet/global-earthquake-history-1m-since-1900))
- **Time Span**: 1900 to present (~2026)
- **Records**: ~864,000 events (after cleaning).
- **Attributes**: Includes `time`, `latitude`, `longitude`, `depth`, `mag`, `place`, `type`, and more.

---

## 🔄 The Analytical Workflow

The project is structured into 5 phases, mapping directly to the notebook sections:

1. **01 Data Quality Validation**:
   - Dropped columns with >50% nulls.
   - Imputed missing `depth` and `mag` with median values.
   - Converted `time` to datetime (handling `+00:00` timezone offsets).
   - Removed duplicate records.
   - Removed extreme outliers on `depth` only (preserving magnitude).

2. **02 Documentation & Knowledge**:
   - Built a comprehensive data dictionary.
   - Summarized descriptive statistics and documented assumptions (e.g., mixing magnitude scales).

3. **03 Data Analysis & Investigation**:
   - Analyzed temporal trends (exponential growth in recorded events due to improved technology).
   - Visualized global spatial distribution (Ring of Fire).
   - Conducted deep dive into depth distributions (discovering the 10km & 33km bimodal peaks).

4. **04 Data Storytelling & Visualization**:
   - Built an optimized interactive timeline (using hexbin/heatmap to avoid overplotting).
   - Redesigned the spatial density map using `matplotlib.hexbin` to render globally without external tile servers.
   - Created seasonal analysis (no seasonal impact—earthquakes are random).

5. **05 Stakeholder Communication**:
   - Summarized findings into 3 actionable recommendations for engineers and emergency planners.
   - Built a mock-up executive dashboard using `plotly.subplots`.
---

## 🚀 How to Run This Project

1. **Clone the repository**:
   ```bash
   git clone https://github.com/mudecharannaik/tectonic-insights-earthquake-analysis.git
   cd tectonic-insights-earthquake-analysis

# 📈 Key Insights & Takeaways
- Magnitude matters: Large earthquakes (M>8.0) are statistically rare but physically critical. They were preserved in the dataset.

- Depth is bimodal: The vast majority of earthquakes occur at ~10 km (crustal) and ~33 km (upper mantle). There is no peak at 100 km.

- Spatial density: The Pacific Ring of Fire, the Himalayan belt, and the Mediterranean-Asian zone are the world's primary seismic hotspots.

- Seasonality: Earthquakes occur uniformly throughout the year—no seasonal predictability.

