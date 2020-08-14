# Creating Customer Segments
Analyzing a dataset containing data on various customers' annual spending amounts (reported in monetary units) of diverse product categories for internal structure. One goal of this project is to best describe the variation in the different types of customers that a wholesale distributor interacts with. Doing so would equip the distributor with insight into how to best structure their delivery service to meet the needs of each customer.

The dataset for this project can be found on the <a href="https://archive.ics.uci.edu/ml/datasets/Wholesale+customers"> UCI Machine Learning Repository.</a> For the purposes of this project, the features 'Channel' and 'Region' will be excluded in the analysis — with focus instead on the six product categories recorded for customers.

<hr> </hr>

## Data Exploration:
The dataset is composed of six important product categories: 

- 'Fresh' 
- 'Milk' 
- 'Grocery' 
- 'Frozen' 
- 'Detergents_Paper'
- 'Delicatessen'

### Percentile for Each Sample:
<img src="https://github.com/geekquad/Customer-Segments/blob/master/img/each_Sample_percentage.png">

#### Customer Index : 25 (Index 0)
- Major Spending: Fresh, DetergentS_Paper (Based on "HeatMap" & "> mean_value")
- Medium Spending: Milk, Grocery (Based on "HeatMap" & "Around mean_value")
- Minor Spending: Frozen, Delicatessen (Based on "HeatMap" & "< mean_value")
    - **Conclusion: Small Retail Store.**

#### Customer Index : 50 (Index 1)
- Major Spending: Frozen, Delicatessen (Based on "HeatMap" & "> mean_value")
- Medium Spending: Fresh, Detergents_Paper (Based on "HeatMap" & "Around mean_value")
- Minor Spending: Milk, Grocery (Based on "HeatMap" & "< mean_value")
    - **Conclusion: Restaurant**

#### Customer Index : 75 (Index 2)
- Major Spending: Frozen, Fresh (Based on "HeatMap" & "> mean_value")
- Medium Spending: Delicatessen (Based on "HeatMap" & "Around mean_value")
- Minor Spending: Milk, Grocery, Detergents_Paper (Based on "HeatMap" & "< mean_value")
    - **Conclusion: Supplier (with Small Resturent Business) / Supermarket (with attached Small Restaurant)**
    
### Feature Distribution
<img src="https://github.com/geekquad/Customer-Segments/blob/master/img/feature%20distribution.png">

<hr> </hr>

## Data Preprocessing

### Feature Scaling:
<img src="https://github.com/geekquad/Customer-Segments/blob/master/img/feature%20scaling.png">

Distribution before Normalizing the Data:

<img src="https://github.com/geekquad/Customer-Segments/blob/master/img/before%20normalizing.png">

Distribution after Normalizing the Data:

<img src="https://github.com/geekquad/Customer-Segments/blob/master/img/after%20normalilzing.png">

<hr> </hr>

## Feature transformation

### PCA Implementation:

<img src="https://github.com/geekquad/Customer-Segments/blob/master/img/pca%20implementation.png">

### Dimension Reductinality:
<img src="https://github.com/geekquad/Customer-Segments/blob/master/img/dimension%20reductionality.png">

### Visulaizing Biplot:
A biplot is a scatterplot where each data point is represented by its scores along the principal components. The axes are the principal components (in this case Dimension 1 and Dimension 2). In addition, the biplot shows the projection of the original features along the components. A biplot can help us interpret the reduced dimensions of the data, and discover relationships between the principal components and original features.

<img src="https://github.com/geekquad/Customer-Segments/blob/master/img/biplot.png">

<hr> </hr>

## Clustering:
Choosing Gaussian Mixture Model algorithm because of its ability to apply "soft" classification and since we've reduced the dimensionality of the problem with PCA, GMM should be able to do the job.

### GMM Clustering Visualization:
<img src="https://github.com/geekquad/Customer-Segments/blob/master/img/gmm%20cluster.png">

<hr> </hr>

## Visualizing Underlying Distributions

<img src="https://github.com/geekquad/Customer-Segments/blob/master/img/underlying%20distributions.png">

#### Final Conclusion:
- The actual data appears to correlate very strongly with our predicted clusters earlier. It shows that the GMM clustering was able to establish the key relationships very well. It wasn't able to capture some of the more anamolous data points - particularly Retailers lying within the Hotel/Restaurant/Cafe cluster.

- The actual distribution has a less well defined seperation between clusters, but it can be stated with reasonable confidence.

- Yes, they are almost exactly the guesses I made regarding their classification - Cluster 0 I thought to be Restaurants/Cafes (I didn't consider hotels) and Cluster 1 being Bulk Distributor or Supermarkets, which is analagous to retailers.





























