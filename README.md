# CryptoClustering
 unsupervised learning

 The file crypto_clustering.ipynb was used for the coding purpose using Jupyter notebook. Crypto_market_data.csv was loaded into a DataFrame for further use. 

 Step 1: Prepare the Data
 . StandardScalar() module from scikit-learn was used to normalize the data from the csv file.
 . The Dataframe was created with the scaled data and "coin_id" was set as the index from the original DataFrame as the index of the new scaled Dataframe.

 STEP 2: Find the best value for k using the original scaled dataframe
 Elbow curve method was used to find the best value for k. Following steps were taken;
  - A list with the number of k values from 1 to 11 was created.
  - an empty list to store the inertia values was created.
  - a for loop to compute the inertia with each possible value of k.
  - a dictionary with the data to plot the elbow curve.
  - a line chart was plotted with all the inertia values computed with the different values of k to visually identify the optimal value for k.
  - From the plot it was found that the best value for k is 4.

STEP 3: Cluster cryptocurrencies with k-means using the original scaled data
The following steps were taken to cluster the cryptocurrencies for the best value for k on the original scaled data:
- initialize the k-means model with the best value for k.
- fit the k-means model using the original scaled dataframe
- predict teh clusters to group the cryptocurrencies using the original scaled dataframe.
- Create a copy of the original data and add a new column with the predicted clusters.
- Create a scatter plot using hvPlot with x-axis as "PC1" and y-axis as "PC2.

STEP 4: Optimize clusters with principal component analysis
- using the original scaled DataFrame, perform a PCA and reduce the features to three principal components.
- Retrieve the explained variance to determine how much information can be attributed to each principal component which is 88%
- Create a new DataFrame with the PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

STEP 5: Find the best value for k using the PCA data
The elbow method was used on the PCA data to find the best value for k using the following steps:
- Create a list with the number of k-values from 1 to 11.
- Create an empty list to store the inertia values.
- Create a for loop to compute the inertia with each possible value of k.
- Create a dictionary with the data to plot the Elbow curve.
- Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.
- From the plot it was clear that the best value for k using the PCA data was also 4.

STEP 6: Cluster cryptocurrencies with k-means using PCA data
Following steps were used:
- Initialize the K-means model with the best value for k.
- Fit the K-means model using the PCA data.
- Predict the clusters to group the cryptocurrencies using the PCA data.
- Create a copy of the DataFrame with the PCA data and add a new column to store the predicted clusters.
- Create a scatter plot using hvPlot.

Result: The clusters are more distinct when using the PCA. 
