# Analysing Data

### Aggregating Data

When you are working with a dataset it may be necessary to add some columns or data to be able to see the big picture. This are the most common examples of aggregations 
in data:
- The count of how many registers you have in the dataset.
- The total of all the column.
- How many possibilities you have in a categorial column.
- Average of the Data.
- Mininimal value.
- Maximum value.


### Grouping and Summarizing

Another common action when working with data is to group the data when you have a categorial variable. This is really helpful to see in which category you have better
results than the other also it is easier to visualize this kind of insight. Here is a small example of this.

| Price   |Day	  |Sales | Revenue |
| :---:   |:---:  |:---: |:---:	   |
| 37      |Monday | 2    | 74      |
| 37  	  |Tuesday| 23   |851	   |
| 55  	  |Monday | 45   |24755	   |
| 55 	  |Tuesday| 50   |2750	   |

Here you can see there are the sales of 4 days, two are repeated but with a different price one from the other. Where it comes the importance of grouping and summarizing 
is first you group the sales per price.

| Price   |Day	  |Sales | Revenue |
| :---:   |:---:  |:---: |:---:	   |
| 37      |		  |      | 	       |
|         |Monday | 2    | 74      |
|    	  |Tuesday| 23   |851	   |
| 55  	  |       |      |   	   |
|   	  |Monday | 45   |24755	   |
|   	  |Tuesday| 50   |2750	   |

Then after having this table it would be a good idea to have the summary per price.

| Price   |Day	  |Sales | Revenue |
| :---:   |:---:  |:---: |:---:	   |
| **37**  |**2**  |**25**| 	**925**|
|         |Monday | 2    | 74      |
|    	  |Tuesday| 23   |851	   |
| **55**  |**2**  |**95**|**27505**|
|   	  |Monday | 45   |24755	   |
|   	  |Tuesday| 50   |2750	   |

With this you are able to see that in the Mondays, of course it is more helpful with more data, it is better to sell with a price of **55** as well as in Tuesday.But as a 
final touch it is helpful to have a quick **total** summary at the end.

| Price   |Day	  |Sales  | Revenue |
| :---:   |:---:  |:---:  |:---:	|
| **37**  |**2**  |**25** | **925** |
|         |Monday | 2     | 74      |
|    	  |Tuesday| 23    |851	    |
| **55**  |**2**  |**95** |**27505**|
|   	  |Monday | 45    |24755    |
|   	  |Tuesday| 50    |2750	    |
|**Total**|**4**  |**120**|**28430**|


## Visualysing Data

About this part I would understand if you believe it is the easisest part about using data, actually in many cases I have seen it is a really difficult topic for many people.
This is why I will give you a quick guide of which type of graphs exist and how you should use them.

### Line graph

Line graphs are used to track changes over short and long periods of time.

#### Tips 
- When smaller changes exist, line graphs are better to use than bar graphs. 
- Line graphs can also be used to compare changes over the same period of time for more than one group.

### Pie Chart

Pie charts are best to use when you are trying to compare parts of a whole. 

#### Tips
- They do not show changes over time.

###Bar Graph.

Bar graphs are used to compare things between different groups or to track changes over time. 

### Tips
- When trying to measure change over time, bar graphs are best when the changes are larger.

###Area Graph.

They can be used to track changes over time for one or more groups. 

### Tips
- Area graphs are good to use when you are tracking the changes in two or more related groups that make up one whole category (for example public and private groups).

