# Cryptocurrencies

## Overview of the analysis:
Accountability Accounting, a prominent investment bank, is interested in offering a new cryptocurrency investment portfolio for its customers. The company, however, is lost in the vast universe of cryptocurrencies. So, they have requested to create a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for this new investment.

The data that will be working with is not ideal, so it will need to be processed to fit the machine learning models. Since there is no known output for what is being asked for, it has been decided to use unsupervised learning. To group the cryptocurrencies, clustering algorithm has been chosen to perform the analysis. The use of data visualizations is utilized to share the findings with the board.

## Results: 
### ***Deliverable 1: Preprocessing the Data for PCA***
Preprocess the dataset in order to perform PCA
  - The following five preprocessing steps have been performed on the crypto_df DataFrame:
    - All cryptocurrencies that are not being traded are removed.
    ![image](https://user-images.githubusercontent.com/106962921/194889040-b0c1a8a1-7d78-431f-8d7d-023b8331a6cd.png)
        
    - The IsTrading column is dropped.
    - 
    ![image](https://user-images.githubusercontent.com/106962921/194890770-349cc0e2-171e-4a51-bd42-84607f7331b1.png)
        
    - All the rows that have at least one null value are removed.
     
    ![image](https://user-images.githubusercontent.com/106962921/194891423-2e91ccab-e2f6-4e6d-87ee-36d7405e13d1.png)
        
    - All the rows that do not have coins being mined are removed.
    ![image](https://user-images.githubusercontent.com/106962921/194891687-43913a22-9ded-4408-a634-9f5597646675.png)

    
    - The CoinName column is dropped.
    ![image](https://user-images.githubusercontent.com/106962921/194892495-dcff39a4-8cf3-4b77-8c8b-ea9f3f925714.png)  
    
  - A new DataFrame is created that stores all cryptocurrency names from the CoinName column and retains the index from the crypto_df DataFrame
   
  ![image](https://user-images.githubusercontent.com/106962921/194892168-e8de7173-97d1-4986-bae0-334c7f861f1d.png)
  
  - The get_dummies() method is used to create variables for the text features, which are then stored in a new DataFrame, X
  
  
  - The features from the X DataFrame have been standardized using the StandardScaler fit_transform() function     
 

### ***Deliverable 2: Reducing Data Dimensions Using PCA***
Reduce the dimensions of the X DataFrame to three principal components and place these dimensions in a new DataFrame using PCA algorithm
  - The PCA algorithm reduces the dimensions of the X DataFrame down to three principal components
  
  
  - The pcs_df DataFrame is created and has the following three columns, PC 1, PC 2, and PC 3, and has the index from the crypto_df DataFrame


### ***Deliverable 3: Clustering Cryptocurrencies Using K-means***
Create an elbow curve using hvPlot to find the best value for K from the pcs_df DataFrame created in Deliverable 2. Then, run the K-means algorithm to predict the K clusters for the cryptocurrencies’ data.
  - The K-means algorithm is used to cluster the cryptocurrencies using the PCA data, where the following steps have been completed:
    - An elbow curve is created using hvPlot to find the best value for K
    
    
    - Predictions are made on the K clusters of the cryptocurrencies’ data
    
    
    - A new DataFrame is created with the same index as the crypto_df DataFrame and has the following columns: Algorithm, ProofType, TotalCoinsMined, TotalCoinSupply,     PC 1, PC 2, PC 3, CoinName, and Class 


### ***Deliverable 4: Visualizing Cryptocurrencies Results***
Visualize the distinct groups that correspond to the three principal components created in Deliverable 2, then create a table with all the currently tradable cryptocurrencies using the hvplot.table() function.
  - The clusters are plotted using a 3D scatter plot, and each data point shows the CoinName and Algorithm on hover
  
  
  - A table with tradable cryptocurrencies is created using the hvplot.table() function
  
  
  - The total number of tradable cryptocurrencies is printed
  
  
  - A DataFrame is created that contains the clustered_df DataFrame index, the scaled data, and the CoinName and Class columns
  
  
  - A hvplot scatter plot is created where the X-axis is "TotalCoinsMined", the Y-axis is "TotalCoinSupply", the data is ordered by "Class", and it shows the CoinName   when you hover over the data point


## Summary:
