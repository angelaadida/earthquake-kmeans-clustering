# 🌍 Earthquake Clustering — KMeans Algorithm

Unsupervised machine learning project applying **KMeans Clustering** on 782 earthquake records to discover hidden patterns and natural groupings in seismic data.

---

## 🎯 Problem Statement

Using earthquake sensor data (magnitude, depth, significance, location, etc.), group earthquakes into natural clusters **without predefined labels** — discovering hidden patterns in seismic activity worldwide.

- **Dataset**: 782 earthquakes (2001–2023)
- **Algorithm**: KMeans Clustering
- **Optimal clusters (k)**: 6 → improved to 8

---

## 🔄 ML Pipeline

### Step 1: Exploratory Data Analysis (EDA)
- Missing value analysis (367 missing in `alert`, 576 in `continent`)
- Correlation heatmap of numerical features
- Feature distribution plots, skewness & kurtosis analysis
- Outlier detection using IQR boxplots

### Step 2: Drop Irrelevant Features
Removed: `title`, `location`, `net`, `date_time`, `country`

### Step 3: Data Preprocessing
- **Numerical**: Median imputation → IQR outlier capping → RobustScaler
- **Categorical**: Mode imputation → OneHotEncoding (`alert`, `magType`, `continent`)

### Step 4: Dimensionality Reduction
- Applied **PCA** (2 components) for visualization

### Step 5: Elbow Method
- Tested k = 1 to 14
- Identified optimal k = **6** from elbow curve

### Step 6: KMeans Clustering & Evaluation

| Run | k | Silhouette Score | Inertia (SSE) |
|-----|---|-----------------|---------------|
| Initial | 6 | 0.197 | 2358.32 |
| Improved | 8 (k-means++) | **0.27** | 2719.99 |

### Step 7: Visualization
- Scatter plot: Magnitude vs Depth colored by cluster
- Centroid visualization overlay

---

## 📊 Results & Interpretation

With **k=8 clusters** using `k-means++` initialization:
- **Silhouette Score: 0.27** — moderate cluster separation
- Clusters reveal distinct earthquake groupings by depth, magnitude, and geographic region
- Shallow earthquakes (low depth) tend to cluster separately from deep seismic events

---

## 🛠️ Tech Stack

| Category | Tools |
|----------|-------|
| Language | Python |
| Data Analysis | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn, Missingno |
| Preprocessing | Scikit-learn (SimpleImputer, RobustScaler, OneHotEncoder) |
| Dimensionality Reduction | PCA (Scikit-learn) |
| Clustering | KMeans (Scikit-learn) |
| Evaluation | Silhouette Score, Inertia (SSE) |

---

## 🚀 How to Run

```bash
pip install pandas numpy matplotlib seaborn scikit-learn missingno ydata-profiling
```

Open `KMeans_Clustering_earthquake_week7_sub.ipynb` in Jupyter Notebook and run all cells.

---

## 📁 Project Structure

```
earthquake-kmeans-clustering/
│
├── KMeans_Clustering_earthquake_week7_sub.ipynb   # Main notebook
├── earthquake_data.csv                             # Dataset
└── README.md
```

---

## 🔗 Related Projects

- [Earthquake Magnitude Regression](https://github.com/angelaadida/earthquake-magnitude-regression)

---

## 👩‍💻 Author

**Angela** — Data Scientist | AI • ML • GenAI • RAG  
📍 Kuala Lumpur, Malaysia  
🔗 [GitHub](https://github.com/angelaadida)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
