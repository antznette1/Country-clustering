# Country-clusters

Based on diverse criteria, various definitions of a developing country have been developed. Economic factors are occasionally employed. Other times, social metrics like life expectancy and educational attainment are used to classify a nation as developed or developing.
We will group nations for this work based on social, economic, and health criteria. It's important to highlight that this categorisation preserves the distinctiveness and individuality of these nations.
Unsupervised learning techniques like cluster analysis or clustering strive to optimise the similarity of data within a cluster and the dissimilarity between clusters. Market segmentation, pattern recognition, image analysis, information retrieval, bioinformatics, data compression, computer graphics, and machine learning are just a few of the industries that employ it. Types of clustering include Affinity Propagation, Agglomerative Clustering, DBSCAN, K-Means, Mean Shift, Gaussian Mixture Model, etc., but for this task, we would be considering KMeans clustering.
For this analysis, model 3 gave the most accurate result. I stuck with only Kmeans as my model produced an optimum result. Please refer to source script countries_clustering.py for details.


Data Wrangling


This is fixing or removing incorrect, corrupted, incorrectly formatted, duplicate, or incomplete data within a data set, for this task. We import the necessary data, view the data, and check for missing values. It is essential because it improves the data quality and, in so doing, increases overall productivity. Fortunately, there are no missing values in this data set. We drop the country column as they contain categorical data and wont be useful for our analysis.


Model Building


For model 1 and model 2, random values of k were chosen and the features chosen are in the same scale; hence no need for feature scaling. Model 2 was only built for 3d visualization. For model 3, The inputs were normalized to reduce the scale using a standard scalar method. Please be aware that since the k-means algorithm relies on Euclidean distance, having two features with differing sizes can cause issues. Create a scree plot to identify the best value of K to utilise in the clustering (a line plot that helps determine the number of clusters). The ideal value of k is determined by the Elbow point. The best values for k in this case are either 3, 4, or 5. The sum of square errors decreases linearly after these points. For this analysis, 4 is the best value for K. We further verified our chosen value for k by calculating the silhouette score, confirming four as the best. Since features are in different scales, feeding the k value and the scaled data frame (X-scaled) to the K-Means algorithm is the best approach. Then calculate the mean value of k to get the value for each cluster. We had 4 clusters; cluster 1, cluster 2, cluster 3, and cluster 4. Data visualization was the final process of assigning a colour to each cluster, making it easier to read using plotly.


Evaluation


For model 3, the First cluster has four countries: It has the lowest child mortality rate,
highest GDPP & Income, and the lowest Inflation. In addition, this group contains countries with stable economies, and health care is given that it has the highest life expectancy.
Conversely, the second cluster has 30 countries with the 2nd lowest child mortality rate and 2nd highest GDPP & Income. Also, its Inflation is 2nd lowest. It has significantly higher spending on Health, and the economy can be considered ok.
The third cluster with 87 countries has the 2nd highest child mortality rate, 2nd lowest GDPP & Income, and its Inflation is 2nd highest.
The fourth cluster has the highest child mortality rate and lowest GDPP & Income, and its Inflation is significantly higher than other groups. Countries in this group will be most disadvantaged, but this is based on the data provided
Comparing model 1 and model 3, there is a significant difference in the number of countries per cluster and even those in the same cluster. This is because of the number of features used.


Conclusion


K-means separates all countries in the dataset into a logic based on the features. For model 3, the cluster Fourth, are countries with the worst Health, mortality, and net income indices while the cluster first goes for the opposite side, with countries with the best metrics.
Kmeans did an excellent job in clustering but had some flaws. For example, China, India and Russia were tagged in the same bunch of Third and fourth clusters. Which we know could be a better comparison, primarily due to the economic size and political influence.
The significant difference between the clusters is how they can improve the Net income per person from the size of GPD per capita. Because even though some countries have an economic size and political influence, they are not able to improve their population's quality of life (This is based on the information given)
