# Sorting Results

## Order BY
Use ORDER BY to sort results by one or more columns.
- Aliases created in SELECT clause are visible to ORDER BY
- You can order by columns in the source that are not included in the SELECT clause.
- You can specify ASC or DESC (ASC is the default)

### Examples:

SELECT ProductCategory AS Category, ProductName 
FROM Production.Product
ORDER BY Category, Price DESC;

## Top 

TOP allows you to limit the number or percentage of rows returned by a query. Works with ORDER BY clause to limit rows by sort order.

### Example

Added to SELECT clause:
- SELECT TOP (N)| TOP(N) Percent
    - With percent, number of rows are rounded up
- SELECT TOP(N) WITH TIES
    - Retrieve duplicates where applicable (nondeterministic)

SELECT TOP 10 ProductName, ListPrice
FROM Production.Product
ORDER BY ListPrice DESC

## OFFSET-FETCH
OFFSET-FETCH is an extension to the ORDER BY clause:

- Allows filtering a requested range of rows
    - Dependent on ORDER BY clause
- Provide a mechanism for paging through results
- Specify number of rows to skip, number of rows to retrieve

### Example

ORDER BY <order by list>
OFFSET <offset_value> ROW(S)
FETCH FIRST|NEXT <fetch_value> ROW(S) ONLY
