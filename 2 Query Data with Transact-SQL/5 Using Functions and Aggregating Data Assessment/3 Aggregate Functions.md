# Aggregate Functions

Functions that operate on sets, or rows of data. It summarizes the input rows and without a GROUP BY clause, all rows are arranged as one group.

## **Example**

It counts the number of products and different categories that exist.

SELECT Count(*) AS Products, COUNT(DISTINCT ProductCategoryID) AS Categories, AVG(ListPrice) AS AveragePrice FROM SalesLT.Product;

## Grouping with GROUP BY

GROUP BY creates groups for output rows, according to a unique combination of values specified in the GROUP BY clause, also you can calculate a summary value for aggregate functions in subsequent phases. 

**Note**
- Detail rows are lost after GROUP BY clause is processed.

## **Example**

SELECT c.Salesperson,ISNULL(SUM(oh.SubTotal),0.00)SalesRevenue
FROM SalesLT.Customer c
LEFT JOIN SalesLT.SalesOrderHeader oh
ON c.CustomerID = oh.CustomerID
GROUP BY c.Salesperson, CONCAT(c.FirstName+'',c.LastName)
ORDER BY SalesRevenue DESC, Customer;
