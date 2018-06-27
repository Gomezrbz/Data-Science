# Classification
Classification is another supervised technique to predict which class or category something belongs to. 

## Binary Classification
If it belongs to one of the two classes, if it is true or false. This is by having a threshold which helps to classify if it is of one category or the other one,
this is by having the threshold in the middle lets say 0.5 and if the value tends more to 0 then it is a **negative** if it tends more o the 1 it is **positive**.

Because this is a supervised technique you need to have some known labels to test your model results. After doing this you can get:

| Values 				  |Description			  |
| :---:                   |:---:  				  |
| **True Positive**       |In this case it was a 1|
| **True Negative**       |In this case it was a 0| 
| **False Positive****    |It was a 0 not a 1     |	
| **False Negative****    |It was a 1 not a 0     |	

You can move the threshold to have less false positives or negatives. 

### Metrics

For this metrics you will need the following table

![Table](https://github.com/Gomezrbz/Data-Science/blob/master/1%20Introduction%20to%20Data%20Science/Images/Table.png)

#### Accuracy

![Accuracy](https://github.com/Gomezrbz/Data-Science/blob/master/1%20Introduction%20to%20Data%20Science/Images/Accuracy.png)

#### Precision

![Precision](https://github.com/Gomezrbz/Data-Science/blob/master/1%20Introduction%20to%20Data%20Science/Images/Precision.png)

#### Recall

![Recall](https://github.com/Gomezrbz/Data-Science/blob/master/1%20Introduction%20to%20Data%20Science/Images/Recall.png)

#### True Positive Rate and False Positive Rate
TPR= Recall

![TPR_FPR](https://github.com/Gomezrbz/Data-Science/blob/master/1%20Introduction%20to%20Data%20Science/Images/TPR_FPR.png)

# Clustering
Is a unsupervised technique where you don't have labels to train the model. But you have an algorithm to look for similarities and groups them into clusters.

## K-means clustering
TO understand this remember the data consists of rows of observations and each row has multiple features. 

1. Have features in a graph of n dimensions.
2. Put K points representing the clusters.
3. Assign the features to the nearest K point.
4. Move the K points to the true center of the points in its cluster.
5. Repeat until you have nicely separated clusters.

## Metrics

- Compare the average distance between the clusters centers and the average distance between the clusters centers and the points in their cluster.
Cluster sets that maximize this ratio have the greatest separation.

- Compare the average distance between the clusters centers and the maximum distance between the points and the centroid of the cluster.

- Principal Component Analysis or PCA which decomposes the points of the cluster into directions




