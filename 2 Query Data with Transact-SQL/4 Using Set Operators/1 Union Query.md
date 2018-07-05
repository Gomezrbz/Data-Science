# Union Query

## What is

It is a combination of all the statements or queries given, it also removes any duplicates during query processing(affects performance) but if you don't mind of the duplicates you can do a UNION ALL which retains the duplicates during query processing. In the Union you need to have the same type of data and same number of columns
 
**Note**
- If you know there are no duplicates use UNION ALL to not waste all the process of looking for them.
- The only aliases taken in account is from the first query.


## Example

SELECT countryregion,city FROM HR.Employee 
UNION
SELECT countryregion, city FROM Sales.Customers;

# Intersect and Except

## What is

Intersect are the distinct rows that appear in both result sets. This helps you to know how many **duplicates** are taking in account what appears in both tables.

## Example

SELECT countryregion, city FROM HR.Employees
INTERSECT
SELECT countryregion, city FROM Sales.CUstomers;

# Except

## What is

Except are the distinct rows that appear in the first set but not the second.

**Note**

- Order in which sets are specified matter.

## Example

SELECT countryregion,city FROM HR.Employees
EXCEPT
SELECT countryregion,city FROM Sales.Customers;