# Gene-Expression-Analysis-and-Clustering-GSE45827-
This project performs exploratory analysis, feature selection, clustering, and dimensionality reduction on the publicly available GSE45827 gene expression dataset. The goal is to investigate whether biological groups (e.g., tumor subtypes) can be distinguished based on gene expression patterns.
Workflow
1. Data Loading
The dataset is downloaded using GEOparse.
A gene expression matrix is constructed:
Rows → genes
Columns → samples
2. Label Extraction
Phenotype metadata is explored to identify relevant labels.
The column source_name_ch1 is used to extract biological group labels.
Labels are cleaned and aligned with the expression matrix.
3. Feature Selection
Gene-wise variance is computed across all samples.
Genes are ranked based on variance.
The top variable genes (e.g., top 50) are selected for downstream analysis.

Rationale: Highly variable genes are more informative for distinguishing between biological groups.

4. Data Standardization
Data is scaled using StandardScaler:
Mean = 0
Standard deviation = 1

Why?
Clustering and dimensionality reduction rely on distance metrics, so scaling ensures that no feature dominates 

5. Hierarchical Clustering (Heatmap)
A clustered heatmap is generated using seaborn. clustermap.
Samples are annotated with their biological group using color labels.

Observation:

Samples tend to cluster according to biological groups.
Distinct gene expression patterns are visible:
Upregulated genes (red)
Downregulated genes (blue)
6. Dimensionality Reduction (t-SNE)
t-SNE is applied to reduce data to 2 dimensions.
Samples are plotted and colored by biological group.

Observation:

Clear separation between groups.
t-SNE provides a more interpretable visualization compared to the heatmap.
Results
Gene expression patterns successfully capture biological differences.
Both clustering and t-SNE show that:
Samples group according to their biological subtype.
t-SNE provides the clearest separation between groups.
Technologies Used
Python
GEOparse
pandas
scikit-learn
seaborn
matplotlib
