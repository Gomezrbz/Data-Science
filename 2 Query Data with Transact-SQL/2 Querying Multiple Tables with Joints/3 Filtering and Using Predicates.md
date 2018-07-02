# Filterig and Using Predicates

This are some of the predicates you can use to filter the data you want as you want it.

| Predicates and Operators   | Description                                                                                             |
| :---:                      | :---:                                                                                                   |
| =<>                        | Compares values for equality/non equality                                                               |
| BETWEEN  	                 | Specifies an inclusive range to test                                                                    |
| LIKE  	                 | Determines whether a specific character string matches a specified pattern, which can include wildcards.|
| AND	                     | Combines two Boolean expressions and returns TRUE only when both are TRUE                               |
|OR                          | Combines two Boolean expressions and returns TRUE if either is TRUE                                     |
|NOT                         | Reverses the result of a search condition.                                                              |

## Example

### WHERE
SELECT Name, Color, Size FROM SalesLT.Product WHERE ProductModelID = 6;

### LIKE
SELECT productnumber, Name, ListPrice FROM SalesLT.Product WHERE ProductNumber LIKE 'FR%';

### BETWEEN
SELECT Name FROM SalesLT.Product WHERE SellEndDate BETWEEN '2006/1/1' AND '2006/12/31';

### IN
SELECT ProductCategoryID,Name,ListPrice FROM SalesLT.Product WHERE ProductCategoryID IN (5,6,7)
