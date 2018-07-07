# Grouping Sets

GROUPING SETS subclause builds on GROUP BY clause
Allows multiple groupings to be defined in same query.

SELECT <column list with aggregate(s)>
FROM <source>
GROUP BY
GROUPING SETS
{
    <column_name>,--one or more columns
    <column_name>,--one or more columns
    ()---empty parenthesis if aggregating all rows
}

## ROLLUP

This provides shortcut for defining grouping sets with combinations that assume input columns from a hierarchy

### Example
SELECT StateProvince, City, COUNT(CustomerID) AS Customers
FROM Sales.vCustomerDetails
GROUP BY ROLLUP(StateProvince,City)
ORDER BY StateProvince,City

## CUBE
CUBE provides shortcut for defining grouping sets in which all possible combinations of grouping sets are created.

### Example
SELECT SalesPersonName, CustomerName, SUM(Amount) AS TotalAmount
FROM Sales.vSalesOrders
GROUP BY CUBE(SalesPersonaName, CustomerName)
ORDER BY SalesPersonName,CustomerName;

# Notes
- Multiple grouping sets present a problem in identifying the source of each row in the result set.
- Nulls could come from the source data or could be a placeholder in the grouping set.
- The GROUPING_ID function provides a method to mark a row with a 1 or 0 to identify which grouping set for the row.

SELECT GROUPING_ID(SalesPersonName) AS SalesPersonGroup,
       GROUPING_ID(CustomerName)AS CustomerGroup,
       SalesPersonName, CustomerName,SUM(Amount) AS Total Amount
FROM Sales.vSalesOrders
GROUP BY CUBE(SalesPersonName,CustomerName)
ORDER BY SalesPersonName, CustomerName;

# Pivot Tables

Pivoting data is rotating data from row-based orientation to a columns based orientation. Distinct values from a single column are projected accross as headings for other columns-may include aggregation.

## Example
SELECT OrderID, Bike, Accessories, Clothing
FROM
    (SELECT OrderID,Category, Revenue FROM Sales.SallesDetails)AS sales
PIVOT (SUM(Revenue)FRO Category IN ([Bikes],[Accessories],[Clothing]))AS pvt

# Unpivoting Data

Unpivoting data is rotating data from a columns-based orientation to a rows-based orientation. Spreads or prit values from one source row into one or more target rows. Each source row becomes on or more rows in result set based on number of columns being pivoted.

## Example
SELECT OrderID, Category,Revenue
FROM
    (SELECT OrderID, Bikes, Accesories, Clothing FROM Sales.SalesByCat)AS pvt
UNPIVOT(Revenue FOR Category IN ([Bikes],[Accesories],[Clothing]))AS unpvt