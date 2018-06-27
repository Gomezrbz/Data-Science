# Machine Learning

**Machine Learning** is a way of using data to train a computer module so that it can predict new data values based on known inputs.This is when 
you give training scenarios to a computer, with data obviously, so he can learn how it should calculate future data. The process of this is the following:

1. Check the historical data(x).
2. Have a predictive value(y).
3. Create a function that predicts values(y) using (x)values.

## Kinds of Machine Learning

### Supervised

You start with observations thath include known values for the variables you want to predict, this are called **labels**. Then using a ML algorithm you train a
model that fits the features to the known label. This one compares the value calculated with the already knonw value. After this you can use it to predicte new values.
 
### Unsupervised

You don't have a know label in the training set. This is trained by finding similarities in the observations. After being trained, each new observation is assigned to a cluster
of observations with similar characterisitics.

## Regression

**Regression** is a supervised technique. The way this funtions is by having the information known (x) for us an have the result (y), by having this and the data of other days you can
calculate the result for every x value. After doing this you could have a graph in which you could see the tendency of y depending from the value of x, but also you are able to see some
errors. 

## Metrics for your model

RMSE Root Mean Squared Error:
![RMSE](https://github.com/Gomezrbz/Data-Science/blob/master/Images/RMSE.png)

MAE Mean Absolute Error: 
![MAE](https://github.com/Gomezrbz/Data-Science/blob/master/Images/MAE.png)

RAE Relative Absolute Error:
![RAE](https://github.com/Gomezrbz/Data-Science/blob/master/Images/RAE.png)

RSE Relative Squared Error
![RSE](https://github.com/Gomezrbz/Data-Science/blob/master/Images/RSE.png)

CoD Coeficient of Determination
![CoD](https://github.com/Gomezrbz/Data-Science/blob/master/Images/CoD.png)


Mean Absolute Error (MAE) and Root Mean Square Error (RMSE) are metrics that measure the residuals (the variance between predicted and actual values) in the same units as the label itself. Both of these metrics indicate that on average, the model is accurate within the result.
Relative Absolute Error (RAE) and Relative Squared Error (RSE) are relative measures of error. The closer these values are to zero, the more accurately the model is predicting.
Coefficient of Determination, sometimes known as R-Squared, is another relative measure of accuracy;the closer it is to 1, the better the model is performing.

