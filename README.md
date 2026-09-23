Seed Variety Grouping using Hierarchical Clustering

Overview
This project groups wheat seeds based on their geometric measurements using Agglomerative Hierarchical Clustering. The actual variety 
labels were not used for clustering and were only used later for validation.

Dataset
The Seeds dataset contains 210 samples with 7 features:

Area
Perimeter
Compactness
Kernel Length
Kernel Width
Asymmetry
Groove Length
EDA

Performed:
Descriptive statistics
Missing-value and duplicate checks
Feature distributions using histograms
Outlier detection using boxplots
Correlation heatmap
Scatter plots

The EDA showed that the features have different scales, so standardization was required.

Clustering
The features were standardized using StandardScaler.

Two linkage methods were compared:
Ward Linkage
Complete Linkage

Dendrograms were generated and the hierarchy was tested with 2, 3, 4, and 5 clusters.

Evaluation
The clustering was evaluated using:

Silhouette Score – measures cluster separation
Adjusted Rand Index (ARI) – compares clusters with actual varieties
Cophenetic Correlation – checks how well the dendrogram preserves distances
Results
Linkage	 Clusters	   Silhouette	      ARI
Ward	     2	        0.4613      	 0.4762
Ward       3	        0.3926	       0.7970
Ward	     4	        0.3006	       0.7309
Ward	     5	        0.2746	       0.6159
Complete	 2	        0.4520	       0.4883
Complete	 3	        0.3502	       0.6863
Complete	 4	        0.3149	       0.6549
Complete	 5	        0.2937	       0.5821

Cophenetic Correlation:
Ward: 0.7286
Complete: 0.7130
Conclusion

The 3-cluster Ward solution showed strong agreement with the known seed varieties, achieving an ARI of 0.7970. 
Overall, hierarchical clustering successfully identified meaningful structure in the seed measurements without using the variety labels during training.
