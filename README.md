# 🏡 Exploring the Impact of Housing on Health in England and Wales: A Visual Analytics Approach

This repository presents a data-driven visual analytics study examining how **housing conditions influence public health** across regions in England and Wales. By combining **UK census data** (2011 & 2021) with **Bayesian predictive modeling for 2031**, this project explores structural relationships using dimensionality reduction and interactive dashboarding tools.

> 🧭 *Objective: Support health-aware housing policy by revealing patterns, changes, and spatial disparities in how people live and feel.*

---

## 📊 Overview

- 📅 **Data**: UK Census 2011 & 2021 (health, housing)
- 📍 **Region**: Local authority level (district & region)
- 🛠️ **Tools**: Tableau, Python (LDA, UMAP, Bayesian Ridge)
- 🎯 **Focus**: Spatial health disparity, temporal forecasting, visual correlation

---

## 🔍 Methods Summary

### 1. 📐 Data Processing

- Merged housing and health datasets from 2011 & 2021
- Standardized regional identifiers
- Cleaned and joined using population-normalized features
- Created derived variables:
  - Housing quality indicators (e.g., % no heating, overcrowding rate)
  - Age-normalized health distributions
  - Health change index (2021 vs 2011)

### 2. 🌐 Dimensionality Reduction

#### 🔸 **LDA (Linear Discriminant Analysis)**
- Used to project regions based on health status labels (e.g. "Good", "Poor")
- Revealed high variance in regions with mixed-quality housing
- Highlighted divergence between affluent South and under-resourced North

#### 🔸 **UMAP**
- Used for unsupervised 2D embedding of housing + health features
- Clustered similar regions based on housing conditions and population density
- Showed distinct housing-health patterns in London vs rural areas

### 3. 📈 Predictive Modeling (2031 Forecast)

#### 🔸 **Bayesian Ridge Regression**
- Trained on 2011 and 2021 features to predict health proportions for 2031
- Included credible intervals (95%) to reflect uncertainty
- Predictive performance evaluated with R² and inspection of residuals

---

## 🌟 Key Results

| Aspect | Insight |
|--------|---------|
| 📉 Health | Decline in "Very Good" health from 2011 to 2021 in most urban zones |
| 🏚 Housing | Overcrowded & non-heated households correlate with worse health |
| 📍 Spatial | Worst health in North West and West Midlands; best in rural South |
| 🔮 Forecast | Bayesian model predicts further urban-rural health divergence by 2031 |
| 🔁 LDA | Groups with high bad health proportions aligned with high % flats and low space |
| 🧭 UMAP | London boroughs form dense cluster separate from rest of country |

---

## 📊 Interactive Visualisation (Tableau)

Built with **Munzner’s task framework** (Overview → Zoom & Filter → Details-on-Demand):

1. **Geographic Health Distribution** (2011 / 2021 / 2031)
2. **Housing Type vs Health Explorer** – scatter matrix + bar charts
3. **LDA & UMAP Region Clusters** – 2D embeddings with hover & compare
4. **Temporal Comparison Dashboard** – regional health change trajectories

Dashboards allow:
- Hover for detail
- Drill-down by region
- Filtering by housing condition, population size, etc.

---

## 📁 Repository Structure

```plaintext
housing-health-visual-analytics/
├── data/
│   ├── raw/                    # Original census files
│   ├── processed/              # Cleaned and merged datasets
├── scripts/
│   ├── preprocessing.py
│   ├── lda_projection.py
│   ├── umap_projection.py
│   └── bayesian_forecast.py
├── tableau/
│   └── housing_health_dashboard.twbx
├── figures/
│   ├── lda_projection.png
│   ├── umap_map_colored.png
│   ├── forecast_comparison.png
├── VA_Report.pdf              # Final visual analytics report
└── README.md
