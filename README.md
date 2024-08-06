# CryptoClustering
OSU AI Bootcamp Module 11 Challenge

**Monday, July 29th, 2024

Explained Challenge to Cosmo/ChatGPT

Created GitHub Repo

# Imported required libraries and dependencies
import pandas as pd
from sklearn.cluster import KMeans
from sklearn.decomposition import PCA
from sklearn.preprocessing import StandardScaler

# Loaded the data into a Pandas DataFrame and make the index the "coin_id" column.
market_data_df = pd.read_csv("Resources/crypto_market_data.csv", index_col="coin_id")

# Displayed sample data
market_data_df.head(10)

# Generated summary statistics
market_data_df.describe()

Now on the 'Prepare the Data' step

**Monday, August 5th, 2024

Now on:

# Create a scatter plot using Pandas plot by setting 
# `x="price_change_percentage_24h"` and `y="price_change_percentage_7d"`.
# Use "rainbow" for the color to better visualize the data.
market_data_clustered_df.plot.scatter(
    x='price_change_percentage_24h', 
    y='price_change_percentage_7d', 
    c='cluster', 
    colormap='rainbow', 
    figsize=(10, 6), 
    title='Cryptocurrency Clusters'
)



This is what I got so far: See attached Crypto_Clustering.ipynb and README.md

ChatGPT
Great progress! Let's continue working through the challenge. Here's what needs to be done next based on your current state:

Prepare the Data:
Use StandardScaler to normalize the data.
Create a new DataFrame with the scaled data, using coin_id as the index.
Find the Best Value for k Using the Original Scaled DataFrame:
Use the elbow method to determine the optimal value for k.
Cluster Cryptocurrencies with K-Means Using the Original Scaled Data:
Cluster the data using the best value for k.
Create a scatter plot to visualize the clusters.
Optimize Clusters with Principal Component Analysis:
Perform PCA to reduce the data to three principal components.
Find the total explained variance of the three components.
Create a new DataFrame with the PCA data.
Find the Best Value for k Using the PCA Data:
Use the elbow method on the PCA data to find the best value for k.
Cluster Cryptocurrencies with K-Means Using the PCA Data:
Cluster the PCA data using the best value for k.
Create a scatter plot to visualize the clusters.
Determine the Weights of Each Feature on Each Principal Component:
Create a DataFrame to show the weights of each feature for each principal component.


# Create a scatter plot using Pandas plot by setting 
# `x="price_change_percentage_24h"` and `y="price_change_percentage_7d"`.
# Use "rainbow" for the color to better visualize the data.
market_data_clustered_df.plot.scatter(
    x='price_change_percentage_24h', 
    y='price_change_percentage_7d', 
    c='cluster', 
    colormap='rainbow', 
    figsize=(10, 6), 
    title='Cryptocurrency Clusters'
)

ChatGPT
Let's break down what this graph means:

Axes:
The x-axis represents the percentage change in cryptocurrency prices over the last 24 hours (price_change_percentage_24h).
The y-axis represents the percentage change in cryptocurrency prices over the last 7 days (price_change_percentage_7d).

Clusters:
Each point represents a cryptocurrency.
The color of each point indicates the cluster it belongs to, with colors ranging from purple (Cluster 0) to red (Cluster 4).

Interpretation of Clusters:
Cryptocurrencies in the same cluster exhibit similar behavior in terms of their price changes over the last 24 hours and the last 7 days.
For instance, if a cluster has points mostly in the top-right quadrant, those cryptocurrencies have positive price changes over both time frames.
Conversely, if a cluster has points in the bottom-left quadrant, those cryptocurrencies have negative price changes over both time frames.

Analysis of Specific Clusters:
Cluster 0 (Purple): Cryptocurrencies in this cluster have mixed performance but are mostly around the origin, indicating smaller price changes.
Cluster 1 (Red): Cryptocurrencies in this cluster show moderate positive changes in the 24-hour period but varied performance over 7 days.
Cluster 2 (Light Blue): Cryptocurrencies in this cluster generally show positive price changes over both periods.
Cluster 3 (Green): Cryptocurrencies here have varied changes but are generally closer to the origin or negative.
Cluster 4 (Orange): This cluster has fewer cryptocurrencies, showing significant negative changes over the last 24 hours and varied changes over 7 days.

Practical Use:
By identifying these clusters, investors can tailor their strategies. For example, they might choose to invest in cryptocurrencies that consistently perform well (positive changes) or avoid those that exhibit high volatility (large negative changes).


Based on the PCA analysis, Monero (XMR) appears to be a potential investment as it is identified in both positive long-term and short/mid-term clusters. This suggests that Monero shows strong positive growth indicators across various timeframes.

**Investment Consideration:

Monero (XMR) is showing potential for both long-term and short/mid-term growth according to the PCA analysis.
However, always consider other factors such as market conditions, project fundamentals, and your own risk tolerance before making any investment decisions.