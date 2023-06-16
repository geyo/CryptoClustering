# Unsupervised Learning to Analyze Cryptocurrencies Susceptibility to Price Change

By Grace Yoo

**Programming Languages & Libraries Used:** Python, Scikit-learn, Pandas
**Concepts:** Unsupervised Learning, K-means, Principal Component Analysis

## Purpose

The purpose of this project is to use unsupervised learning on a toy dataset of cryptocurrencies to examine if these cryptocurrencies are affected by 24-hour or 7-day price changes. Use K-Means Clustering and Principal Component Analysis (PCA)

## Process

The following steps were taken to apply unsupervised learning to the dataset:

1. Examine data.
2. Apply <code> StadardScaler() </code> module to normalize dataset for features that have different ranges and distributions. 
3. Find the best value for <code>k</code> (i.e. the number of clusters the unsupervised learning algorithm should identify) using the elbow method 
  - Find the _inertia_ (i.e. measure of how close the data points are within a cluster) for each value of k using a for loop and a KMeans model. 
  - Plot _inertia_ and <code>k</code> values in a line chart. 
  - Choose the <code>k</code> value that has the sharpest change in slope (aka elbow.)
4. Cluster cryptocurrencies with K-means using the original scaled data and your chosen k value. 
5. In order to compare the effect of optimizing clusters with Principal Component Analysis (PCA), apply PCA after step 2, and repeat steps 3-4. Examine any differences. 

### Findings

In the initial analysis of the data, we find that the ethlend is a lcear outlier, and the sharpest changes are seen in the price_change_percentage_1y line. 

![bokeh_plot](https://github.com/geyo/CryptoClustering/assets/8386502/d188ab83-0e27-42ce-88fb-5eabf10072d7)

#### K-means Clustering

Using the elbow method, we find that 4 is the best value for k. 

![bokeh_plot (1)](https://github.com/geyo/CryptoClustering/assets/8386502/ec8f1e29-7584-4a77-9a57-195251d9a124)

We apply the k-means model using 4 as k, and create the scatter plot. 

![bokeh_plot (2)](https://github.com/geyo/CryptoClustering/assets/8386502/55df800c-38d5-4424-9835-d224ddc10a2d)

#### K-means Clustering with PCA Applied

This time, we optimize the standardized data using Principal Component Analysis (PCA) before applying K-means clustering to see if the results are any different. PCA is used to transform a high-dimensional dataset into a lower dimensional dataset while retaining as much original information as possible. The goal is to capture as much variance within the data as possible. The total explained variance captured using three components was .895. 

When plotting the inertia and possible k values for PCA-applied dataset, we find that there is no difference in results. 

![bokeh_plot (4)](https://github.com/geyo/CryptoClustering/assets/8386502/7acbeadc-5579-419c-b4c3-b755e8280b0d)

![bokeh_plot (5)](https://github.com/geyo/CryptoClustering/assets/8386502/ff2b32b1-9bb2-4906-9d2b-918a8d6e4fe5)

### Conclusion

Question: After visually analyzing the cluster analysis results, what is the impact of using fewer features to cluster the data using K-Means?

Answer: In this case, using fewer features results in no loss of information. The elbow curve is the same. Whereas where each coin has been placed in the scatterplot looks different, the clustering has not changed. How each coin has been clustered is also a 1:1 match between the PCA and the nonPCA charts.
