# Customer-Segmentation

## Introduction:
•	Customer segmentation is the process of separating customers into groups based on their shared behavior or other attributes. The groups should be homogeneous within themselves and should also be heterogeneous to each other.

•	The main goal is to identify customers that are most profitable and the ones who churned out to prevent further loss of customer by redefining company policies.

•	Having large number of customers, each with different needs it is crucial to find which customer are most important for business and target them with appropriate strategy.

## Problem Statement:
Identify major customer segments on a transnational dataset which contains all the transactions occurring between 01/12/2010 and 09/12/2011 for a UK-based and registered non-store online retail.

## Data Description:
•	**InvoiceNo:** Nominal, 6-digit integral number uniquely assigned to each transaction

•	**StockCode:** Nominal, 5-digit integral number uniquely assigned to each distinct product

•	**Description:** Nominal, product(item) name

•	**Quantity:** Numeric, quantities of each product per transaction

•	**InvoiceDate:** Numeric, the day and time when each transaction was generated

•	**UnitPrice:** Numeric, product price per unit in sterling

•	**CustomerID:** Nominal, 5-digit integral number uniquely assigned to each customer

•	**Country:** Nominal, name of the country where each customer resides

## Approach:-
### Data cleaning:
•	Remove null values from CustomerID column

•	Remove duplicate entries

•	Remove negative values from Quantity

•	Keep UnitPrice greater than zero

### Data preparation:
•	Extract feature ‘Recency’ from last date of entries and InvoiceDate column

•	Get ‘Frequency’ of transaction per CustomerID

•	Calculate ‘Monetary Value’ for each customer from item purchased and unit price 

•	Perform Log-transformation to remove skewness in data distribution

## Clustering:
•	Use K-Means clustering algorithm to make clusters

•	Use the Elbow method and silhouette analysis to get number of clusters

•	Assign clusters to each CustomerID

•	Take mean of features for each cluster to interpret RFM Score 

## Conclusion:

|Cluster|RFM Interpretation|Type of Customer|
|---|---|---|
|0 |Last purchase long ago, <br />Least number of transactions, <br />Least monetary spending	|Churned|
|1 |Recent transaction, <br />Most frequent transactions, <br />Highest monetary spending |Best (target)|
|2 |Recent transaction, <br />Low purchase frequency, <br />Low monetary spending	|New|
|3 |Last purchase while ago, <br/>Less frequent transactions, <br />Low monetary spending	|At Risk|
