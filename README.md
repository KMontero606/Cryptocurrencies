# Cryptocurrencies
![image](https://user-images.githubusercontent.com/106962921/194949263-c9d7e72d-d7e9-4730-a142-2482647cc85a.png)

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
  <img width="844" alt="image" src="https://user-images.githubusercontent.com/106962921/194945835-494c20b1-3cf2-4123-9c2a-cddef17c98da.png">
  
  - The features from the X DataFrame have been standardized using the StandardScaler fit_transform() function
  <img width="443" alt="image" src="https://user-images.githubusercontent.com/106962921/194946000-c69a1b58-2676-407b-8e4f-5d80d359bd15.png"> 

### ***Deliverable 2: Reducing Data Dimensions Using PCA***
Reduce the dimensions of the X DataFrame to three principal components and place these dimensions in a new DataFrame using PCA algorithm
  - The PCA algorithm reduces the dimensions of the X DataFrame down to three principal components
  <img width="404" alt="image" src="https://user-images.githubusercontent.com/106962921/194946113-96621c98-11a9-4bae-9a01-c1c8e915866a.png">
  
  - The pcs_df DataFrame is created and has the following three columns, PC 1, PC 2, and PC 3, and has the index from the crypto_df DataFrame
  <img width="616" alt="image" src="https://user-images.githubusercontent.com/106962921/194946186-53dfb209-4b05-4514-ae26-62ae125d9ed3.png">

### ***Deliverable 3: Clustering Cryptocurrencies Using K-means***
Create an elbow curve using hvPlot to find the best value for K from the pcs_df DataFrame created in Deliverable 2. Then, run the K-means algorithm to predict the K clusters for the cryptocurrencies’ data.
  - The K-means algorithm is used to cluster the cryptocurrencies using the PCA data, where the following steps have been completed:
    - An elbow curve is created using hvPlot to find the best value for K
    <img width="641" alt="image" src="https://user-images.githubusercontent.com/106962921/194946966-1adf663a-2976-4c75-830a-469acb59958e.png">
    
    - Predictions are made on the K clusters of the cryptocurrencies’ data
    <img width="412" alt="image" src="https://user-images.githubusercontent.com/106962921/194947055-f3708fbb-4713-49d9-83fa-b120daaf0419.png">
    
    - A new DataFrame is created with the same index as the crypto_df DataFrame and has the following columns: Algorithm, ProofType, TotalCoinsMined, TotalCoinSupply,     PC 1, PC 2, PC 3, CoinName, and Class
    <img width="565" alt="image" src="https://user-images.githubusercontent.com/106962921/194947154-8c29f99e-bd2a-436f-9713-ca7c0bbee85b.png"> 

### ***Deliverable 4: Visualizing Cryptocurrencies Results***
Visualize the distinct groups that correspond to the three principal components created in Deliverable 2, then create a table with all the currently tradable cryptocurrencies using the hvplot.table() function.
  - The clusters are plotted using a 3D scatter plot, and each data point shows the CoinName and Algorithm on hover
  <img width="643" alt="image" src="https://user-images.githubusercontent.com/106962921/194947536-cdf684ed-6c56-4b82-83fe-8ebc2f6e82b8.png">
  
  - A table with tradable cryptocurrencies is created using the hvplot.table() function
  <img width="640" alt="image" src="https://user-images.githubusercontent.com/106962921/194947689-6c284029-280b-4d9c-94aa-aa7891afa84e.png">
  
  - The total number of tradable cryptocurrencies is printed
  <img width="374" alt="image" src="https://user-images.githubusercontent.com/106962921/194947742-9a210e9c-f45f-4d4f-9ed7-f96e949c24ff.png">
  
  - A DataFrame is created that contains the clustered_df DataFrame index, the scaled data, and the CoinName and Class columns
  <img width="607" alt="image" src="https://user-images.githubusercontent.com/106962921/194947802-8491f8ca-81e2-4e12-9ecf-a3f645a619d6.png">
  
  - A hvplot scatter plot is created where the X-axis is "TotalCoinsMined", the Y-axis is "TotalCoinSupply", the data is ordered by "Class", and it shows the CoinName   when you hover over the data point
  <img width="589" alt="image" src="https://user-images.githubusercontent.com/106962921/194947910-8a8e56bf-4ea4-4835-9a7e-80f5d8ab17d9.png">
