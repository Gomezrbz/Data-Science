# Subqueries

## What is

This are nested queries: queries within queries. The results of inner query passes to outer query.
- Inner query acts like an expression from perspective of outer query.
- You can have as results:
    - Single value (Scalar subquery)
    - Multiple values (Multi-valued subquery)

## Example


SELECT MAX(UnitPrice) FROM SalesLT.SalesOrderDetail
> This query tells you which is the maximum value of that attribute.

SELECT * FROM SalesLT.Product
WHERE ListPrice > 1467.01
> Checks all the products that are above that value given **manually**.

If you want to have this info for any value you would need to do the next query.
> SELECT * FROM SalesLT.Product WHERE ListPrice > (SELECT MAX(UnitPrice)FROM SalesLT.SalesOrderDetail)

## Self Contained Query and Correlated

Most of the subqueries are self-contained and have no connection with the outer query other than passing it results. About the Correlated subqueries, this ones reger to elements of tables used in the outer query and have the following characteristics:
- Dependent on outer query, cannot be executed separately.
- Behaves as if inner query is executed once per outer row.
- May return scalar value or multiple values.

## Example

SELECT orderid, empid, orderdate
FROM Sales.Orders AS O1
WHERE orderdate = (SELECT MAX(orderdate)
                    FROM Sales.Orders AS O2
                    WHERE O2.empid= O1.empid)
ORDER BY empid, orderdate

# Apply Operator

CROSS APPLY applies the right table expression to each row in left table
- Conceptually similar to CROSS JOIN between two tables but can correlate data between sources.

## Example

SELECT S.supplierid, s.companyname, P.productid, P.productname, P.unitprice
FROM Production.Suppliers AS S
CROSS APPLY dbo.fn_TopProductsByShipper(S.supplierid) AS P

OUTER APPLY adds rows for those with NULL in columns for right table.
- Similar to LEFT OUTER JOIN between two tables.