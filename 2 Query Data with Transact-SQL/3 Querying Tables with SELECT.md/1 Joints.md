# Joints

The **concept** is to combine the rows from multiple tables by specifying matching criteria.
- Usually based on primary key foreign key relationships
- For example, return rows that combine data from the Employee and SalesOrder tables by matching the Employee.EmployeeID primary key to the SalesOrder.EmployeeID foreign key.

### Syntax

ANSI SQL-92
- Tables joined by JOIN operator in FROM Clause
    - Preferred Syntax
        - SELECT.....FROM Table1 JOIN Table2 ON <on_predicate>;
ANSI SQL-89
- Tables joined by commas in FROM Clause
    - Not recommended: Accidental Cartesian products!
        - SELECT.....FROM Table1, Table2 WHERE <where_predicate>;

# Inner Joint

Return only rows where a match is found in both input tables. Match rows based on attributes supplied in predicate. If join predicate operator is =, also known as equi-join.

## Example

SELECT emp.FirstName, ord.Amount 
FROM HR.Employee AS emp
[INNER] JOIN Sales.SalesOrder AS ord
ON emp.EmployeeID= ord.EmployeeID

# Outer Joint

Return all rows from one table and any matching rows from second table. One table's rows are "preserved"
- Designated with LEFT, RIGHT, FULL keyword.
- All rows from preserved table output the result set.

Matches from other table retrieved.

Additional rows added to results for non-matched rows.
- Nulls added in places where attributes do not match.

## Example

Return all employees and for those who have token orders, return the order amount. Employees without matching orders will display NULL for order amount.

SELECT emp.FirstName, ord.Amount FROM HR.Employee AS emp LEFT [OUTER] JOUN Sales.SalesOrder AS ord ON emp.EmployeeID = ord.EmployeeID

# Cross Joints

Combine each row from first table with each row from second table. All possible combinatios output.
Logical foundation for inner and outer joins
- Inner join starts with Cartesian product, adds filter
- Outer join takes Cartesian output, filtered, adds back non-matching rows (with NULL placeholders)

Due to Cartesain product output, not typically a desired form of join
- Some useful exception:
    - Table of numbers, generating data for testing


## Example

SELECT emp.First Name, prd.Name
FROM HR.Employee AS emp
CROSS JOIN Production.Product AS prd;

# Self Join

Compare rows in same table to each other. Create two instances of same table in FROM clause.
- At least one alias required

## Example
Return all employees and the name of the employee's manager.

SELECT emp.FirstName AS Employee, man.FirstName AS Manager
FROM HR.Employee AS emp
LEFT JOIN HR.Employee AS man 
ON emp.ManagerID = man.EmployeeID