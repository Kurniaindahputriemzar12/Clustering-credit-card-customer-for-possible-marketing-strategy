# Clustering-credit-card-customer-for-possible-marketing-strategy
The sample Dataset summarizes the usage behavior of about 8950 active credit card holders. The file is at a customer level with 18 behavioral variables. You need to develop a customer segmentation to define marketing strategy from the dataset.

**OBJECTIVE**
There are a lot of features in this dataset (18 behavioral features). We will now perform:
- Data preprocessing
- Clustering
- Feature extraction with PCA
- Choosing the number of clusters
- EDA to segment the customers
- Concluding the project by giving possible marketing strategy based on data

**DATA DESCRIPTION**

Following is the Data Dictionary for Credit Card dataset:

- CUST_ID: Identification of Credit Card holder (Categorical)
- BALANCE: Balance amount left in their account to make purchases
- BALANCE_FREQUENCY: How frequently the Balance is updated, score between 0 and 1 (1 = frequently updated, 0 = not frequently updated)
- PURCHASES: Amount of purchases made from account
- ONEOFF_PURCHASES: Maximum purchase amount done in one-go
- INSTALLMENTS_PURCHASES: Amount of purchase done in installment
- CASH_ADVANCE: Cash in advance given by the user
- PURCHASES_FREQUENCY: How frequently the Purchases are being made, score between 0 and 1 (1 = frequently purchased, 0 = not frequently purchased)
- ONEOFF_PURCHASES_FREQUENCY: How frequently Purchases are happening in one-go (1 = frequently purchased, 0 = not frequently purchased)
- PURCHASES_INSTALLMENTS_FREQUENCY: How frequently purchases in installments are being done (1 = frequently done, 0 = not frequently done)
- CASH_ADVANCE_FREQUENCY: How frequently the cash in advance being paid
- CASH-ADVANCE_TRX: Number of Transactions made with "Cash in Advanced"
- PURCHASES_TRX: Number of purchase transactions made
- CREDIT_LIMIT: Limit of Credit Card for user
- PAYMENTS: Amount of Payment done by user
- MINIMUM_PAYMENTS: Minimum amount of payments made by user
- PRC_FULL_PAYMENT: Percent of full payment paid by user
- TENURE: Tenure of credit card service for user

**DATA CLEANING**
One of the most important preprocessing steps in a Data Science project. In this project, I imputed missing values with the median value, dropped the CUST_ID column, then normalized the input values using StandardScaler().

**CLUSTERING**
Correlation check
![image](https://user-images.githubusercontent.com/93784445/150670225-62bbbcd5-97f4-482b-866c-1624fa3ed619.png)
- there are 3 redundant features
- "PURCHASES" and "ONEOFF_PURCHASES" = 0.92
- "PURCHASES_FREQUENCY" and 'PURCHASES_INSTALLMENT_FREQUENCY' = 0.86
- "CASH_ADVANCE_TRX" and "CASH_ADVANCE_FREQUENCY" = 0.8

**CLUSTERING USING K-MEANS**
![image](https://user-images.githubusercontent.com/93784445/150670321-5581561c-6597-4033-8feb-1b8c38a3a7bf.png)
Using the elbow method, we pick a good number of clusters to be  5 or 6.

**SILHOUTTE SCORE**

Silhouette analysis can be used to study the separation distance between the resulting clusters. The silhouette plot displays a measure of how close each point in one cluster is to points in the neighboring clusters and thus provides a way to assess parameters like number of clusters visually.
- Silhouette-Score for 2 Clusters:  0.20951117145873602
- Silhouette-Score for 3 Clusters:  0.2504160232402912
- Silhouette-Score for 4 Clusters:  0.1976791965228765
- Silhouette-Score for 5 Clusters:  0.19325195080511473
- Silhouette-Score for 6 Clusters:  0.2027304988653554

**Silhouette plot :**
![image](https://user-images.githubusercontent.com/93784445/150670492-346f263f-d12f-4d41-b214-5c3fb7349abd.png)
![image](https://user-images.githubusercontent.com/93784445/150670497-d8b669ff-7357-470f-8b0d-daf65c8dc52a.png)
![image](https://user-images.githubusercontent.com/93784445/150670510-7b36184b-64e5-4dbf-9509-c8a747fddb73.png)
![image](https://user-images.githubusercontent.com/93784445/150670586-17511e90-2d9f-4c89-a2b1-a2eb149e7c73.png)
![image](https://user-images.githubusercontent.com/93784445/150670592-f13cc4a2-043f-419a-bdd3-141b9349e327.png)

**Feature Extraction with PCA**
PCA with # of components:  2
- Silhouette-Score for 2 Clusters:  0.4597327687456667        Inertia:  48011.944779642276
- Silhouette-Score for 3 Clusters:  0.44711981051287303        Inertia:  31903.246595339155
- Silhouette-Score for 4 Clusters:  0.4054100376824246        Inertia:  23719.961847599
- Silhouette-Score for 5 Clusters:  0.40031766930516427        Inertia:  18754.26551419331
- Silhouette-Score for 6 Clusters:  0.38125514107479247        Inertia:  15686.76535891859

PCA with # of components:  3
- Silhouette-Score for 2 Clusters:  0.33645686007731673        Inertia:  60066.84868065934
- Silhouette-Score for 3 Clusters:  0.371621103162713        Inertia:  44932.81809577861
- Silhouette-Score for 4 Clusters:  0.3617257322234474        Inertia:  33910.13430651664
- Silhouette-Score for 5 Clusters:  0.3603650697969346        Inertia:  28081.16120157631
- Silhouette-Score for 6 Clusters:  0.31912545899303146        Inertia:  24436.1089805379

PCA with # of components:  4
- Silhouette-Score for 2 Clusters:  0.30238369865751713        Inertia:  70883.15665518887
- Silhouette-Score for 3 Clusters:  0.3363332324549488        Inertia:  55874.20292299039
- Silhouette-Score for 4 Clusters:  0.3177587304799692        Inertia:  44087.45773096999
- Silhouette-Score for 5 Clusters:  0.3151170837438338        Inertia:  38169.36687228418
- Silhouette-Score for 6 Clusters:  0.28641666532942495        Inertia:  34286.57211714321

PCA with # of components:  5
- Silhouette-Score for 2 Clusters:  0.27787605376577207        Inertia:  80072.25417696292
- Silhouette-Score for 3 Clusters:  0.3099236627568685        Inertia:  65001.07315684903
- Silhouette-Score for 4 Clusters:  0.2837864886822611        Inertia:  53273.11447247588
- Silhouette-Score for 5 Clusters:  0.2805840137727129        Inertia:  47199.57705599285
- Silhouette-Score for 6 Clusters:  0.2783003355547676        Inertia:  42038.543151181264

PCA with # of components:  6
- Silhouette-Score for 2 Clusters:  0.260370818562087        Inertia:  88373.86152713449
- Silhouette-Score for 3 Clusters:  0.29234066994070246        Inertia:  73352.26674128605
- Silhouette-Score for 4 Clusters:  0.2650081199664101        Inertia:  61286.6523497939
- Silhouette-Score for 5 Clusters:  0.25752925139559957        Inertia:  55045.403817534956
- Silhouette-Score for 6 Clusters:  0.25502103789724445        Inertia:  49812.702672548534

**GAUSSIAN MIXTURE CLUSTERING**
![image](https://user-images.githubusercontent.com/93784445/150670665-c3759c05-4673-4b86-a9e4-ded7f65ae25e.png)

**Exploratory Data Analysis**
![image](https://user-images.githubusercontent.com/93784445/150670839-67a80053-37ac-433c-97bb-27aad908074a.png)
![image](https://user-images.githubusercontent.com/93784445/150670853-c81a343c-7144-4363-ae62-cb0189953a47.png)
![image](https://user-images.githubusercontent.com/93784445/150670991-e23cac30-da4b-40d3-9d60-3ac86741206e.png)

# SUMMARY
- Cluster 0 do not use credit card very much in their daily life. They have healthy finances and low debts. While encouraging these people to use credit cards more is necessary for the company's profit, business ethics and social responsibility should also be considered.
- Identify active customers in cluster 3 in order to apply proper marketing strategy towards them. These people are the main group that we should focus on.
- Some people are just bad at finance management - for example, the Money Borrowers. This should not be taken lightly.
- Although we are currently doing a good job at managing Cluster 2 by giving them low credit limits, more marketing strategies targeting this group of customers should be considered.







