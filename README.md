# Cryptocurrencies
Using unsupervised machine learning to discover patterns about cryptocurrencies.

## Data Preprocessing 
In this project we have read the crypto_data.csv dataset into a Pandas DataFrame and preprocessed it for the machine learning clustering algorithm: 
<ul>
  <li>we deleted the currencies which are not traded at the market and the ones without coins mined,</li>
  <li>we removed the rows without algorithm or containing NULL values,</li>
  <li>then we converted text values into numerical data and scaled the dataset using StandardScaler from the sklearn library.</li>
</ul>

## Reducing Dimensionality
We used the PCA algorithm from sklearn to reduce the dimensions of the scaled DataFrame.
Thus we obtained the following three-dimensional dataset:<br>
<img src="https://github.com/marczuka/Cryptocurrencies/blob/master/Pictures/Dataset_PCA.png" width=300>

## Clustering Cryptocurrencies Dataset
In order to use the clustering KMeans algorithm from sklearn we first created an elbow curve to find out the optimal value for K.
Our elbow curve turned out showing that the most drastical corner is at the point 4.<br>
<img src="https://github.com/marczuka/Cryptocurrencies/blob/master/Pictures/Elbow_curve.png" width=600>

Then we rum the K-means algorithm on our dataset to predict 4 clusters for the cryptocurrencies' data.
After that we created a summury DataFrame containing our cruptocurrencies parameters, PCA dimensions and predicted cluster numbers stored in a column "Class".<br>
<img src="https://github.com/marczuka/Cryptocurrencies/blob/master/Pictures/Dataset_clustered.png" width=800>

## Visualizing Results
To visualize the obtained clusters of the cryptocurrencies we created a 3D scatter plot:<br>
<img src="https://github.com/marczuka/Cryptocurrencies/blob/master/Pictures/3D_plot.png" width=800>

Then we created a data table with all the currently tradeble cryptocurrencies using hvplot library:<br>
<img src="https://github.com/marczuka/Cryptocurrencies/blob/master/Pictures/Table.png" width=800>

And finally, we created a scatter plot to present the clusted data about cryptocurrencies having x="TotalCoinsMined" and y="TotalCoinsSupply" to 
contrast the number of available coins versus the the total number of mined coins using hvplot library as well:<br>
<img src="https://github.com/marczuka/Cryptocurrencies/blob/master/Pictures/Scatter_plot.png" width=600>
