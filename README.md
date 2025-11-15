# Customer Segmentation — Sales Performance Optimization for Superstore

Short description
- Reproducible notebook-based project to perform exploratory data analysis, preprocessing, dimensionality reduction (PCA), and unsupervised clustering to produce customer/product segments from Superstore transactional data. The goal is to identify actionable groups to improve targeting, inventory decisions, and sales strategies.

Project outcomes
- Clustered dataset exports:
  - ifood_df_with_clusters.csv (clusters on numeric features)
  - ifood_df_with_clusters_full.csv (clusters on combined numeric + encoded categorical features)
- Persisted artifacts for reuse:
  - scaler_full.joblib
  - pca_full.joblib
  - kmeans_full.joblib
- Visual outputs and summaries:
  - PCA scatter plots, elbow & silhouette charts, cluster profiles (group means & sizes)
- Findings (example):
  - X distinct customer segments identified (silhouette-based selection)
  - Cluster profiles outline high-value vs low-value segments and behavioral patterns useful for targeting and promotions.

Data
- Primary example: `ifood_df.csv` (Sample - Superstore or equivalent transactional CSV).
- Notebook reads this CSV, performs cleaning (drops irrelevant columns), handles missing values, and encodes categoricals for combined-feature modeling.

Repository structure (key files)
- csg.ipynb — main notebook with full workflow (EDA → preprocessing → PCA → KMeans → profiling)
- ifood_df.csv — sample raw data (expected input)
- ifood_df_with_clusters.csv, ifood_df_with_clusters_full.csv — outputs
- scaler_full.joblib, pca_full.joblib, kmeans_full.joblib — model artifacts
- outputs/ — example aggregated outputs and reports (optional)

Tools & technologies
- Python (pandas, numpy)
- scikit-learn (StandardScaler, PCA, KMeans, silhouette_score)
- seaborn, matplotlib (visualization)
- joblib (artifact persistence)
- Jupyter Notebook (reproducible analysis)

How to run (quick)
1. Open `csg.ipynb` in Jupyter or VS Code and run cells top-to-bottom.
2. Ensure `ifood_df.csv` is in the notebook working directory or update the path in the data-loading cell.
3. Review the elbow and silhouette plots to confirm chosen k, then inspect `ifood_df_with_clusters_full.csv` for cluster assignments.
4. Use the saved joblib artifacts to run inference on new rows without rerunning the full notebook.

Reproducibility & tips
- Random seeds are set for PCA and KMeans for deterministic runs.
- Categorical encoding: one-hot for low-cardinality, frequency-encoding for high-cardinality. Adjust strategies as needed.
- If memory or performance is a concern, reduce dimensionality or sample the dataset before hyperparameter sweeps.

Next steps / improvements
- Add automated unit tests and a small CLI or script to load artifacts and score new data.
- Try alternative clustering algorithms (DBSCAN, Agglomerative) and use cluster explainability (SHAP-like summaries or feature importances) for interpretable segments.
- Build dashboard (Streamlit/Power BI) to visualize segments and business KPIs by cluster.

License & contact
- Add a LICENSE file appropriate to your use.
- For questions, open an issue or contact the project owner listed in repository metadata.


