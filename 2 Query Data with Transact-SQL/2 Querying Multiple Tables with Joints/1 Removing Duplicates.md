# Removing Duplicates

This part is using the SELECT statement. For example:

SELECT Color FROM Production.Product;

| Color   |
| :---:   | 
| Blue    |
| Red	  |
| Yellow  |
| Blue    |
|Yellow   |
|Black 	  |

As you can see with this query you would get all the colors you have for every product, but if you only want the colors you have you need to use **DISTINCT**

SELECT DISTINCT Color FROM Production.Product;

| Color   |
| :---:   | 
| Blue    |
| Red	  |
| Yellow  |
| Black   |