## SELECT Statement

With this table I believe it covers all what you can do with the **SELECT** statement.

| Element | Expression      |Role|
| :---:   | :---:           | :---:|
| SELECT  | Select list     |Defines which columns to return|
| FROM    | Table Source    |Defines table(s) to query|
| WHERE   | Search Condition|Filter rows using a predicate|
| GROUP BY| Group By List   |Arranges rows by group|
| HAVING  | Search Condition|Filter groups using a predicate|
| ORDER BY| Order By List   |Sorts the output|

## Order
- FROM Know from where you want to get your information.
- WHERE Know which are the specifics of the information you need **if needed**..
- GROUP BY Group the information by a domain in particular **if needed**.
- HAVING Search for an specific trait in the domains **if needed**..
- ORDER BY Remember the information without this it wouldn't have any order in specific **if needed**..
- SELECT Which **domains** you need as a result.

## Examples

### All Columns

SELECT * FROM Production.Product;
 #### Note
 (*) Means all the domains.

### Specific Columns

SELECT Name, ListPrice
FROM Production.Product;

### Expressions and Aliases

SELECT Name AS Product, ListPrice * 0.9 AS SalesPrice
FROM Production.Product;



