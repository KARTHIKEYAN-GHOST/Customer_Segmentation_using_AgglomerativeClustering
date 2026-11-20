# Customer Segmentation — Current K-Means Implementation

The repository name refers to Agglomerative Clustering, but the checked-in script `kmeans_clustering.py` imports and trains `sklearn.cluster.KMeans`. It does **not** currently implement Agglomerative Clustering. This README describes the code that is actually present.

## Dataset

`Mall_Customers.csv` contains the following columns:

- `CustomerID`
- `Genre`
- `Age`
- `Annual_Income_(k$)`
- `Spending_Score`

The current script maps `Genre` to numeric values, but the clustering input uses only `Age` and `Spending_Score`.

## Implementation

The script:

1. Loads the customer dataset with pandas.
2. Inspects the dataframe.
3. Encodes `Genre` as `Male = 1` and `Female = 0` (the encoded column is not used in the model).
4. Uses `Age` and `Spending_Score` as the two clustering features.
5. Fits K-Means models for cluster counts 1 through 10 and plots within-cluster sum of squares (WCSS) for the elbow method.
6. Fits a five-cluster K-Means model and displays the cluster assignments and inertia.
7. Plots the five clusters and their centroids.

## Technology

- Python
- pandas
- NumPy
- Matplotlib
- scikit-learn

## Run locally

```bash
git clone https://github.com/KARTHIKEYAN-GHOST/Customer_Segmentation_using_AgglomerativeClustering.git
cd Customer_Segmentation_using_AgglomerativeClustering

python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install pandas numpy matplotlib scikit-learn
```

The script currently reads `/content/Mall_Customers.csv`, a Google Colab path. Change it to `pd.read_csv("Mall_Customers.csv")` for local execution, then run:

```bash
python kmeans_clustering.py
```

## Output

The program displays an elbow-method chart and a two-dimensional scatter plot with five K-Means clusters and their centroids.

## Repository naming note

If the intention is to demonstrate Agglomerative Clustering, replace the K-Means implementation with `sklearn.cluster.AgglomerativeClustering` and update the workflow and visualizations. Until then, the current project should be described as K-Means customer segmentation.
