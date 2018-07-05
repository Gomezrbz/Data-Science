# Logical Functions

Test on the data to compare it and have a result.

## **Examples**

ISNUMERIC
> Check if it is a numeric value
>.....WHERE ISNUMERIC(Size)-1

IIF
>After a condition asign a value.
> IIF(ProductCategoryID IN (5,6,7), 'Bike','Other')...........

CHOOSE
>After a condition asign a value.
>........CHOOSE(cat.ParentProductCategoryID,'Bikes','Components','Clothing', 'Accesories')...........

# Window Functions

This are functions applied to a window, or set of rows.

## **Example**
In this example it will rank the Products by the List Price, something you should know is that by ranking more than one row can get the same value because they have the same listprice so if there were 3 rows with a ListPrice of 100 the next row ranked will be 4 no 2.

SELECT TOP(100) ProductID, Name,ListPrice
RANK() OVER(ORDER BY ListPrice DESC)AS RankByPrice
FROM SalesLT.Product AS p
ORDER BY RankByPrice


