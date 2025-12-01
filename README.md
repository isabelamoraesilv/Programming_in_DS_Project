# 🌋 Volcanic Eruptions Analysis: From Data to Dashboard

![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![Dashboard](https://img.shields.io/badge/Dashboard-Dash%20%2F%20Plotly-orange)
![ML](https://img.shields.io/badge/Machine%20Learning-Scikit--Learn-green)

## 📋 Project Overview

This project applies the **Knowledge Discovery in Databases (KDD)** process to a historical dataset of volcanic eruptions (NOAA). The goal is to clean, transform, mine, and visualize data to uncover patterns in global volcanic activity.

We move beyond simple statistics to implement **Data Mining algorithms** (Linear Regression, K-Means Clustering) and **Data Enrichment** (via external APIs) to produce a fully interactive **Analytical Dashboard**.

**Course:** Programming for Data Science 
---

## ⚙️ The KDD Process

Our approach follows the standard Data Science pipeline:

### 1. Data Cleaning & Preprocessing
* **Handling Missing Data:** Imputed missing casualty counts with 0 (based on historical reporting standards).
* **Type Casting:** Standardized Year, Latitude, Longitude, and VEI columns.
* **Filtering:** Removed records lacking temporal or spatial dimensions essential for analysis.

### 2. Indicator Construction & Feature Engineering
* **Mortality Analysis:** Differentiated between **Direct deaths** (Lava, Ash) and **Indirect deaths** (Tsunamis, Earthquakes).
* **VEI Discretization:** Transformed the logarithmic Volcanic Explosivity Index (0-8) into categorical buckets (Low, Moderate, Violent) to visualize the **Frequency-Magnitude Paradox**.

### 3. Data Mining (Machine Learning)
* **Temporal Trend Analysis (Regression):** Used **Linear Regression** to model eruption frequency over centuries.
    * *Insight:* Demonstrated the **"Recency Bias"** (or Hockey Stick effect), proving that the increase in recorded eruptions is due to better technology/population growth, not geological changes.
* **Spatial Analysis (Clustering):** Applied **Unsupervised K-Means Clustering** on coordinates.
    * *Insight:* The algorithm automatically "discovered" the tectonic plates (Pacific Ring of Fire) without using any map shapefiles.

### 4. Data Enrichment (External Source)
* Integrated the **World Population Dataset** via the `kagglehub` library.
* Created a derived metric: **Deaths per Million Inhabitants**.
* *Result:* Shifted the risk perspective from large countries (Indonesia) to vulnerable island nations (Martinique, St. Vincent).

### 5. Interactive Dashboard
Built a reactive web application using **Python Dash**:
* **Row 1:** Mortality Bar Chart (Toggle: Raw Deaths vs. Normalized Risk).
* **Row 2:** Donut Chart (Power) & Geo Map (Tectonic Clusters).
* **Row 3:** Temporal Line Chart (Regression Trend).

---

## 📊 Key Visualizations

> *Tip: Add screenshots of your dashboard here*

### The Lethality Paradox
We demonstrated that while **Violent eruptions (VEI 5+)** account for less than 10% of events, they are responsible for the vast majority of historical deaths.

### The Geography of Risk
Our K-Means analysis identified three major zones:
1.  **The Asian Giant (Indonesia/Japan):** High frequency, massive death toll.
2.  **The Americas:** Higher average explosivity (VEI).
3.  **Southwest Pacific:** High activity, lower human impact.

---

## 🛠️ Installation & Usage

### Prerequisites
* Python 3.x
* Pip

### Libraries
Install the required packages:
```bash
pip install pandas numpy plotly dash scikit-learn kagglehub
