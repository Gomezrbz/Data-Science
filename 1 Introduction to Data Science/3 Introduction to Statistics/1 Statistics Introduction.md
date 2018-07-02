# Statistics

This is at the core of Data Science. With this you can:
- Distribution of the data 
- Variance of the values
- Influence of the values in others.

This is by understanding the discriptive statistics used to understand the distribution of the data.

### Measuring Central Tendency

To review this it is important to have the following values.

| Values needed |Description			   |
| :---:         |:---:  				   |
| **Max**       |Maximum value 			   |
| **Min**       |Minimal value			   | 
| **Mean**      |The average of the values | 
| **Median**    |The value in the middle   |
| **Mode**    	|Most common value   	   |	 

To review the frecuency from your dataset you may want to use an histogram. After doing this there are some cases the mode could have a peak in the data set but also 
the mean, median and mode are more centrally allocated giving us symmetric tails on the left and right, this is called **normal distribution**. You can see an example in the following image.

![Normal Distribution](https://github.com/Gomezrbz/Data-Science/blob/master/1%20Introduction%20to%20Data%20Science/Images/normal_distribution.PNG)


### Measuring Variance

As you were able to see in the Image of normal distribution there is some variance between the data and the way to calculate it is the following:

![Variance](https://github.com/Gomezrbz/Data-Science/blob/master/1%20Introduction%20to%20Data%20Science/Images/Variance.png)

The only problem is that because we end up with something in a different scale we need to get the square root, this one is called standard deviation.

![Standard Deviation](https://github.com/Gomezrbz/Data-Science/blob/master/1%20Introduction%20to%20Data%20Science/Images/Standard_Deviation.png)

The higher is the SD it is the variance between the data. And just for you to know there other two possibilities of types of distribution right and left. This happens when the mean median and mode tend to one extreme or the other and are called skewed Distributions.

### Working with samples

When you are working with samples you have the problem you may not be working with the full population of the samples. This doesn't mean you are wrong or that you need to work with such a large dataset. 
Instead of here are some tips you can take in account for this issue:

- Create an historic of samples and get their mean.
- Use as much population as you can.
- Get the mean of the random group of samples you got, this way it will be approximate to the mean of the full population.

### Correlation 

This part is to find relation between data in a quantifiable way. A correlation can be as the following:

| Type of correlation |Description			   							 |
| :---:         	  |:---:  				   							 |
| **+1**       	  	  |Indicates a positive relationship between the data(one increases and the other one as well)|
| **0**       	      |There isn't any relation		   | 
| **-1**      	      |Indicates a negative relationship between data(one increases and the other one decreases) |

