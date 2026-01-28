# Analysis of Gene Expression Profiles for Cancer Subtyping

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Scikit-Learn](https://img.shields.io/badge/Library-Scikit--Learn-orange)
![Bioinformatics](https://img.shields.io/badge/Domain-Bioinformatics-green)

## 📌 Project Overview
This project applies **unsupervised machine learning** techniques to high-dimensional gene expression data (RNA-Seq) to identify distinct cancer subtypes. 

The goal was to determine if transcriptomic data alone—without clinical labels—is sufficient to distinguish between five different types of tumors: **BRCA** (Breast), **COAD** (Colon), **KIRC** (Kidney), **LUAD** (Lung), and **PRAD** (Prostate).

By implementing a pipeline of dimensionality reduction (**PCA**, **t-SNE**) and clustering (**K-Means**), the model achieved a **97% match (ARI Score)** with the ground truth labels, demonstrating the power of genomic signatures in cancer classification.

---

## 🧬 The Data
**Dataset:** [UCI Gene Expression Cancer RNA-Seq](https://www.kaggle.com/datasets/waalbannyantudre/gene-expression-cancer-rna-seq-donated-on-682016?select=data.csv)
* **Samples:** 801 patients
* **Features:** 20,531 genes (High-dimensional RNA-Seq data)
* **Classes:** 5 distinct tumor types

| Cancer Code | Description |
|:---:|:---|
| **BRCA** | Breast Invasive Carcinoma |
| **COAD** | Colon Adenocarcinoma |
| **KIRC** | Kidney Renal Clear Cell Carcinoma |
| **LUAD** | Lung Adenocarcinoma |
| **PRAD** | Prostate Adenocarcinoma |

---

## ⚙️ Methodology (The Pipeline)
1.  **Data Preprocessing:** * Merged gene expression data with clinical labels.
    * Handled missing values and removed non-numerical metadata.
    * Applied **Standard Scaling** (Z-score normalization) to normalize gene expression levels (Mean=0, Variance=1).
    
2.  **Dimensionality Reduction:**
    * **PCA (Principal Component Analysis):** Reduced 20,000+ genes to 2 Principal Components to visualize global variance.
    * **t-SNE (t-Distributed Stochastic Neighbor Embedding):** Applied non-linear dimensionality reduction to resolve overlapping clusters (specifically distinguishing between Colon and Lung subtypes).

3.  **Unsupervised Clustering:**
    * **Elbow Method:** Used to mathematically determine the optimal number of clusters (*k=5*), which aligned perfectly with the biological ground truth.
    * **K-Means Clustering:** Grouped patients into 5 clusters based on their transcriptomic profiles.

---

## 📊 Results & Visualizations

### 1. Principal Component Analysis (PCA)
*PCA successfully separated Kidney (KIRC) and Prostate (PRAD) cancers, but showed overlap between Breast, Lung, and Colon cancers.*


### 2. t-SNE Visualization
*t-SNE successfully unraveled the complex non-linear relationships, creating 5 clear, distinct "islands" for each cancer subtype.*


### 3. Clustering Accuracy
The **K-Means** algorithm (blind to the actual labels) grouped the patients with high precision.


* **Adjusted Rand Index (ARI):** `0.97` (0.0 = Random, 1.0 = Perfect)

---

## 🛠️ Tech Stack
* **Language:** Python
* **Data Handling:** Pandas, NumPy
* **Machine Learning:** Scikit-Learn (PCA, t-SNE, KMeans)
* **Visualization:** Matplotlib, Seaborn

## 🚀 How to Run
1.  Clone the repository.
2.  Install dependencies:
    ```bash
    pip install pandas numpy matplotlib seaborn scikit-learn
    ```
3.  Run the Jupyter Notebook `Gene_Expression_Clustering.ipynb`.
