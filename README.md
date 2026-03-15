# PCA, K-Means and Random Forest Customer Segmentation

This project analyzes credit card customer behavior and builds a **customer segmentation model** using:

- data cleaning and **Exploratory Data Analysis (EDA)**
- **Principal Component Analysis (PCA)** for dimensionality reduction
- **K-Means clustering** to identify customer groups
- **Random Forest** to evaluate which original features most strongly differentiate the clusters

The project is implemented in **Jupyter notebooks** and structured as a sequential analytical pipeline.

---

# Project Goal

The goal of this project is to uncover hidden patterns in customer behavior and identify meaningful customer segments that could be used for:

- personalized marketing campaigns  
- better product targeting  
- analysis of spending and transactional behavior  

---

# Project Structure

```text
pca_kmeans/
├── dataset/
│   ├── CC GENERAL.csv          # original dataset
│   ├── cleaned_data.csv        # cleaned dataset
│   ├── pca_matrix.csv          # PCA projection
│   └── data_clusters.csv       # cleaned data + cluster label
├── notebooks/
│   ├── 01_overview.ipynb       # Data overview
│   ├── 02_pca.ipynb            # PCA step-by-step
│   ├── 03_kmeans.ipynb         # clustering and analysis
│   ├── 04_random_forest.ipynb  # feature importance for clusters
│   └── 05_profiler.ipynb       # additional segment profiling
└── README.md
```

---

# 🧠 Analytical Workflow

## 1) Overview and Data Cleaning (`01_overview.ipynb`)

- Load the original dataset
- Inspect data types, missing values, and basic statistics
- Clean and preprocess the data
- Save the cleaned dataset as `dataset/cleaned_data.csv`
- Perform an initial correlation analysis

---

## 2) PCA (`02_pca.ipynb`)

- Standardize input features
- Compute the covariance matrix
- Calculate eigenvalues and eigenvectors
- Select the number of principal components based on explained variance
- Save the PCA projection to `dataset/pca_matrix.csv`

---

## 3) K-Means (`03_kmeans.ipynb`)

- Determine the optimal number of clusters (Elbow method / inertia)
- Train the K-Means clustering model
- Visualize and analyze cluster profiles
- Assign a `cluster` label to each observation
- Save the labeled dataset to `dataset/data_clusters.csv`

---

## 4) Feature Importance (`04_random_forest.ipynb`)

- Train a **Random Forest classifier** using the original features to predict the cluster label
- Use **feature importance** scores to identify which variables are most responsible for separating the clusters

This step helps interpret the clustering results and understand which customer behavior features drive the segmentation.

---

## 5) Additional Profiling (`05_profiler.ipynb`)

- Perform deeper analysis of individual clusters
- Explore behavioral differences between segments

---

# Dataset and Current State

At the current snapshot in the repository:

- `cleaned_data.csv`: **8636 rows**, **18 columns**
- `pca_matrix.csv`: **8636 rows**, **7 PCA components**
- `data_clusters.csv`: **8636 rows**, **19 columns** (18 features + `cluster`)

Cluster distribution:

- Cluster 0: **3863 observations**
- Cluster 1: **3273 observations**
- Cluster 2: **1165 observations**
- Cluster 3: **335 observations**

---

# Requirements

The project mainly uses the following libraries:

- `numpy`
- `pandas`
- `matplotlib`
- `seaborn`
- `scipy`
- `scikit-learn`
- `Pillow` (PIL)
- `jupyter`

Example installation:

```bash
pip install numpy pandas matplotlib seaborn scipy scikit-learn pillow jupyter
```

---

# How to Run the Project

1. Clone the repository:

```bash
git clone <repo-url>
cd pca_kmeans
```

2. (Recommended) create a virtual environment:

```bash
python -m venv .venv
source .venv/bin/activate
```

3. Install dependencies:

```bash
pip install numpy pandas matplotlib seaborn scipy scikit-learn pillow jupyter
```

4. Start Jupyter:

```bash
jupyter notebook
```

5. Run the notebooks in the following order:

- `01_overview.ipynb`
- `02_pca.ipynb`
- `03_kmeans.ipynb`
- `04_random_forest.ipynb`
- `05_profiler.ipynb`

---

# Possible Future Improvements

- Add a `requirements.txt` or `environment.yml`
- Convert the notebook pipeline into Python scripts (`src/`)
- Add quantitative clustering metrics (silhouette score, Calinski–Harabasz index, etc.)
- Create a short **business interpretation report** describing each customer segment

---

# Dataset Source

Kaggle: **Credit Card Dataset for Clustering**

https://www.kaggle.com/datasets/arjunbhasin2013/ccdata
