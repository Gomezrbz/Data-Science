# Table Expression

## What is a View

This are named queries with definition stored in a database.
- They can provide abstraction, encapsulation and simplification.
- From an administrative perspective, views can provide a security layer to a database.

### Example

CREATE VIEW Sales.vSalesOrders
AS
SELECT oh.OrderID, oh.Orderdate, oh.CustomerID,
        oh.LineItemNo,od.ProductID, od.Quantity
FROM Sales.OrderHeaders AS oh
JOIN Sales.OrderDetails AS od
ON od.OrderID=oh.OrderID

## What is a Temporary Table

Temporary tables are used to hold temporary result sets within a user's session.
- Created in tempdb and deleted automatically
- Created with a # prefix
- Global temporary tables are created with ## prefix
- Can cause recompilation of queries

### Example

CREATE TABLE #tmpProducts
(ProductID INTEGER,
ProductName varchar(50));
GO
.....
SELECT * FROM #tmpProducts;

## What is a Table Variable
 
Introduced because temporary tables can cause recompilations. This are uses similarly to temporary tables but scoped to the batch not to the session. The recommendation is to use it in very small datasets

### Example

DECLARE @varProducts table
(ProductID INTEGER, ProductName varchar(50));
......
SELECT * FROM @varProducts

## What is a Table-Valued Functions

TVFs are named objects with definitions stored in a database.

### Example

CREATE FUNCTION Sales.fn_GetOrderItmes (@OrderID AS Integer)
RETURNS TABLE
AS
RETURN
(SELECT ProductID, UnitPrice, Quantity)
FROM Sales.OrderDetails
WHERE OrderID= @OrderID);
.....
SELECT * FROM Sales.fn_GetOrderItems(1025) AS LineItems;

## What is a Derived Tables

- This are named query expressions created within an outer SELECT statement. 
- Not stored in datbase- represents a virtual realtional table
- Scope of a derived table is the query in which it is defined.

Derived tables must:
- Have an alias
- Have unique names for all columns
- Not use and ORDER BY clause(without TOP or OFFSET/FETCH)
- Not be referred to multiple times in the same query

Derived tables may
- Use internal or external aliases for columns
- Refer to parameters and/or variables
- Be nested within other derived tables

### Example

SELECT orederyear, COUNT(DISTINCT custid) AS cust_count
FROM
    (SELECT YEAR (orderdate) AS orderyear,custid
    FROM Sales.Orders) AS derived_year
GROUP BY orderyear;

## Common Table Expressions
- CTEs are named table expressions defined in a query.
- CTEs are similar to derived tables in scope and naming requirements
- Unlike derived tables, CTEs support multiple references and recursion

### Example

WITH CTE_year(OrderYear,CustId)
AS
(
    SELECT YEAR(orderdate),custid
    FROM Sales.Orders
)
SELECT OrderYear, COUNT(DISTINCT CustID)AS Cust_Count
FROM CTE_year
GROUP BY orderyear;