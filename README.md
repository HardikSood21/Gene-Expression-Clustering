# Analysis of Gene Expression Profiles for Cancer Subtyping

## Project Overview
This project focuses on the unsupervised analysis of high-dimensional transcriptomic data to identify distinct cancer subtypes. Utilizing a suite of statistical machine learning techniques, the workflow reduces the dimensionality of raw gene expression profiles and applies clustering algorithms to discover latent biological patterns without prior labels.

## Methodology
1. **Data Simulation:** Generated high-dimensional synthetic data (150 samples x 10,000 genes) to mimic RNA-Seq count matrices.
2. **Preprocessing:** Applied `StandardScaler` to normalize gene expression variance across samples.
3. **Dimensionality Reduction:** - **PCA:** Reduced feature space from 10,000 to 50 principal components while retaining 95% of variance.
   - **t-SNE:** Visualized the high-dimensional clusters in a 2D manifold.
4. **Clustering:** Implemented **K-Means** to segment patients into distinct molecular subtypes based on their transcriptomic signatures.

## Tech Stack
- **Python**: Core logic.
- **Scikit-Learn**: PCA, t-SNE, K-Means implementation.
- **Pandas/NumPy**: Data manipulation.
- **Seaborn**: Visualization of clusters.

## Key Results
The integration of PCA and K-Means successfully segregated the patient cohort into distinct subtypes, demonstrated by clear separation in the t-SNE latent space.
