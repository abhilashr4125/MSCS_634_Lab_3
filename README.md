# MSCS_634_Lab_3
# Lab 3: K-Means and K-Medoids Clustering

**Name:** Abhilash Reddy Marthala
**Course:** MSCS 634 – Advanced Big Data and Data Mining

## Purpose

Compare K-Means and K-Medoids clustering on the Wine dataset
using Silhouette Score, Adjusted Rand Index (ARI), and
side-by-side visualizations.

## Methods

- Explored 178 samples, 13 features, and three wine classes.
- Standardized all features using z-score normalization.
- Applied K-Means and a custom PAM K-Medoids implementation
  with k = 3 and random_state = 42.
- Used actual class labels only for evaluation.
- Used PCA for visualization; its two components represent
  55.4% of total variance.
- Trained and evaluated both algorithms using all 13
  standardized features.

## Results

| Algorithm | Silhouette Score | Adjusted Rand Index |
|---|---:|---:|
| K-Means | 0.2849 | 0.8975 |
| K-Medoids (PAM) | 0.2676 | 0.7411 |

K-Means achieved slightly better cluster separation and
closer agreement with the actual wine classes in this run.
Both Silhouette Scores indicate moderate separation.

The plots show upper-left, upper-right, and lower groups,
with some overlap between the lower and right-hand groups.
Center positions and some boundary assignments differ.
Cluster numbers and colors are arbitrary across algorithms.

## Challenges and Decisions

Installing scikit-learn-extra failed because compilation
required Microsoft C++ Build Tools. A custom PAM implementation
using NumPy and scikit-learn distance calculations was used instead.

K-Means used 10 initializations, while PAM used one random
initialization. Results may vary with initialization.

K-Means is generally faster for large numerical datasets.
K-Medoids provides actual observations as centers and is
generally more resistant to outliers, but the exhaustive
swap implementation requires more computation.

## Files

- MSCS_634_Lab_3.ipynb: Code, saved outputs, plots, and analysis.
- README.md: Lab overview, results, and decisions.

## How to Run

Install numpy, pandas, scikit-learn, matplotlib, and Jupyter.
Open the notebook and run its cells from top to bottom.
The custom K-Medoids implementation does not require
scikit-learn-extra.
