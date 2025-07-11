# Principal-Component-Analysis-Projects
The project applies and implements PCA and Kernel PCA across multiple datasets to reduce dimensionality, improve supervised learning performance, and visualize clustering structure.

# Problem Statement
<img width="1293" height="102" alt="image" src="https://github.com/user-attachments/assets/fff0f2a4-8fa6-489f-967a-c0923ceb18bc" />

# Solution Summary
- Applied **Principal Component Analysis (PCA)** for dimensionality reduction on:
  - **MNIST**
  - **Spambase**

- **Preprocessing & PCA**:
  - MNIST:
    - Reshaped and normalized pixel values (divided by 255).
    - Applied PCA to reduce to:
      - D = 5 features
      - D = 20 features
  - Spambase:
    - Loaded and prepared tabular data.
    - Applied PCA to find the smallest D achieving near-original performance.

- **Classification Algorithms**:
  - **L2-regularized Logistic Regression**
  - **Decision Trees**

- **Key Results (MNIST)**:
  - Logistic Regression accuracy:
    - D=5 → **0.6875**
    - D=20 → **0.8802**
  - Decision Tree accuracy:
    - D=5 → **0.6715**
    - D=20 → **0.8467**
  - Insight: Preserving more principal components significantly boosts classification performance.

- **Key Results (Spambase)**:
  - Logistic Regression (D=30):
    - Accuracy **0.9099** (vs. original **0.9218** with 57 features)
  - Insight: PCA effectively reduces dimensionality while retaining high classification accuracy.

- **Conclusion**:
  - Demonstrated PCA’s power in reducing data size without major performance loss.
  - Highlighted the balance between dimensionality reduction and model effectiveness across image and tabular datasets.

# Problem Statement
<img width="1899" height="105" alt="image" src="https://github.com/user-attachments/assets/9af4778a-3670-47a4-a322-8466a2cb543f" />

# Solution Summary
- Conducted a **comprehensive study of PCA** for dimensionality reduction on:
  - **MNIST**
  - **Spambase**

- **Custom PCA Implementation**:
  - Developed `PCA_implementation` class:
    - Centered data by subtracting the mean.
    - Computed **covariance matrix**.
    - Extracted **eigenvalues** and **eigenvectors**.
    - Selected top eigenvectors as **principal components**.

- **MNIST Experiments**:
  - Preprocessing:
    - Reshaped images and normalized pixel values (divided by 255).
  - Applied PCA to reduce to:
    - D = 5 features
    - D = 20 features
  - Classification Results:
    - Logistic Regression:
      - D=5 → **0.6858**
      - D=20 → **0.8796**
      - Original → **0.9179**
    - Decision Tree:
      - D=5 → **0.6781**
      - D=20 → **0.8475**
      - Original → **0.8916**
  - Insight: Retaining more principal components improves performance by preserving variance.

- **Spambase Experiments**:
  - Applied PCA with D = 30 features.
  - Logistic Regression Accuracy:
    - PCA D=30 → **0.9131**
    - Original (57 features) → **0.9218**
  - Insight: PCA effectively reduced dimensionality with minimal accuracy loss.

- **Conclusion**:
  - Custom PCA implementation validated across image and tabular datasets.
  - Demonstrated that dimensionality reduction balances feature compression with high model performance.

# Problem Statement
<img width="1263" height="126" alt="image" src="https://github.com/user-attachments/assets/3aaa96e9-e6d3-43e2-98f5-281bfa23e757" />

# Solution Summary

- Conducted a **comprehensive exploration of PCA** for:
  - **Cluster visualization**
  - **Dimensionality reduction for classification performance**

- **Datasets Used**:
  - **MNIST**
  - **Spambase**

- **MNIST Workflow**:
  - Preprocessing:
    - Reshaped images to 2D arrays.
    - Normalized pixel values (divided by 255).
  - Clustering:
    - Applied **K-Means** with:
      - `n_clusters=40`, `random_state=42`, `n_init=3`.
    - Iterative convergence confirmed by decreasing **inertia**.
  - PCA for Visualization:
    - Standardized data using **StandardScaler**.
    - Reduced to **3 principal components** (`n_components=3`).
    - Created **interactive 3D scatter plots** with `plotly.express`:
      - Axes: PC1, PC2, PC3.
      - True digit labels → distinct shapes.
      - K-Means cluster IDs → distinct colors.
      - Highlighted **pure vs. impure clusters**.
    - Additional plots generated using random combinations from top 20 PCs.

- **Classification Performance (MNIST)**:
  - Logistic Regression:
    - D=5 → **0.6858**
    - D=20 → **0.8796**
  - Decision Tree:
    - D=5 → **0.6781**
    - D=20 → **0.8475**
  - Insight: More principal components lead to **higher classification accuracy**.

- **Spambase Workflow**:
  - Applied PCA to reduce to **30 components**.
  - Logistic Regression accuracy:
    - PCA D=30 → **0.9131**
    - Original (57 features) → **0.9218**
  - Insight: PCA achieves **substantial dimensionality reduction** with minimal performance loss.

- **Conclusion**:
  - Combined clustering, visualization, and classification pipelines.
  - Demonstrated PCA’s dual role:
    - Enhancing interpretability (via visualization).
    - Improving computational efficiency (via dimensionality reduction) without sacrificing accuracy.
# Problem Statement
<img width="1257" height="549" alt="image" src="https://github.com/user-attachments/assets/65c7919f-9fc1-48e0-a4da-0ecd60e04489" />
# Solution Summary
- Conducted a **comprehensive exploration of PCA and Kernel PCA** for:
  - **Cluster visualization**
  - **Dimensionality reduction for improved classification**

- **Datasets Used**:
  - **MNIST**
  - **Spambase**
  - **Circles**
  - **Spirals**

- **MNIST Workflow**:
  - Preprocessing:
    - Reshaped images and normalized pixel values (divided by 255).
  - Clustering:
    - Applied **K-Means** with:
      - `n_clusters=40`, `random_state=42`, `n_init=3`.
    - Observed steady decrease in **inertia** (sum of squared distances).
  - PCA for Visualization:
    - Standardized data with **StandardScaler**.
    - Reduced to **3 principal components**.
    - Created **interactive 3D scatter plots** using `plotly.express`:
      - Axes: PC1, PC2, PC3.
      - True labels → distinct shapes.
      - Cluster IDs → distinct colors.
      - Revealed **pure and impure clusters**.

- **MNIST & Spambase Classification**:
  - Logistic Regression (MNIST):
    - D=5 → **0.6858**
    - D=20 → **0.8796**
  - Decision Tree (MNIST):
    - D=5 → **0.6781**
    - D=20 → **0.8475**
  - Logistic Regression (Spambase):
    - PCA D=30 → **0.9131**
    - Original (57 features) → **0.9218**
  - Insight: More principal components → **higher classification accuracy**.

- **Kernel PCA (Custom Implementation)**:
  - Applied to **Circles** and **Spirals** (non-linearly separable datasets).
  - Steps:
    - Compute `X2` and Euclidean distance matrix (`DIST_euclid`).
    - Construct Gaussian kernel matrix `K = exp(-DIST_euclid / sigma)` (sigma = 3).
    - Center kernel matrix `Kn = K - U@K - K@U + U@K@U` (U = ones/N).
    - Perform eigen-decomposition (`np.linalg.eigh`), sort eigenvalues, transform data (`Kn @ V.T`).
  - Results:
    - Logistic Regression (original):
      - Circles → **0.2750**
      - Spirals → **0.6650**
    - Logistic Regression (after Kernel PCA):
      - Circles (8 features) → **100%**
      - Spirals (25 features) → **98.5%**
  - Insight: Kernel PCA dramatically improves linear separability and classification on complex datasets.

- **Conclusion**:
  - Demonstrated PCA and Kernel PCA as powerful tools for:
    - Reducing dimensionality.
    - Improving classification accuracy.
    - Handling non-linear data structures.


