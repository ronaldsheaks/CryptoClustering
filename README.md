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
