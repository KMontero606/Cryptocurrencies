# Cryptocurrencies

## Overview of the analysis:
Accountability Accounting, a prominent investment bank, is interested in offering a new cryptocurrency investment portfolio for its customers. The company, however, is lost in the vast universe of cryptocurrencies. So, they have requested to create a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for this new investment.

The data that will be working with is not ideal, so it will need to be processed to fit the machine learning models. Since there is no known output for what is being asked for, it has been decided to use unsupervised learning. To group the cryptocurrencies, clustering algorithm has been chosen to perform the analysis. The use of data visualizations is utilized to share the findings with the board.

## Results: 
### ***Deliverable 1: Preprocessing the Data for PCA***
Preprocess the dataset in order to perform PCA

### ***Deliverable 2: Reducing Data Dimensions Using PCA***
Reduce the dimensions of the X DataFrame to three principal components and place these dimensions in a new DataFrame using PCA algorithm

### ***Deliverable 3: Clustering Cryptocurrencies Using K-means***
Create an elbow curve using hvPlot to find the best value for K from the pcs_df DataFrame created in Deliverable 2. Then, run the K-means algorithm to predict the K clusters for the cryptocurrencies’ data.

### ***Deliverable 4: Visualizing Cryptocurrencies Results***
Visualize the distinct groups that correspond to the three principal components created in Deliverable 2, then create a table with all the currently tradable cryptocurrencies using the hvplot.table() function.

## Summary:
