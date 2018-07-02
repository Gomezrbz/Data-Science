# Working with Nulls

Nulls means unknown or missing value. ANSI bahaviour for Null values is:
- The result of any expression containing a NULL value is a NULL
    - 2 + NULL = NULL
    - 'MyString: ' + NULL = NULL
- Equality comparissons always return false for NULL values
    - NULL = NULL returns false
    - NULL IS NULL returns true

## Null Functions

- ISNULL(column/variable, value)
    - Returns **vale** if the column or variable is NULL
- NULLIF(column/variable, value)
    - Returns NULL if the column or varibale is value
- COALESCE(column/variable1, column/variable2,...)
    - Returns the value of the first non-NULL column or variable in the list.

## Examples

SELECT Name, ISNULL(TRY_CAST(Size AS Integer), 0) AS NumericSize
FROM SalesLT.Product;

SELECT Name, NULLIF(Color, 'Multi') AS SingleColor
FROM SalesLT.Product

SELECT Name, COALESCE(DiscontinuedDate, SellEndDate, SellStartDate) AS LastActivity 
FROM SalesLT.Product;
