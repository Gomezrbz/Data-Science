# Laboratory 4 questions and answers

1- Write a query that retrieves the company name, first line of the street address, city, and a column named AddressType with the value 'Billing' for customers where the address type in the SalesLT.CustomerAddress table is 'Main Office'. Make sure to use the aliases provided, and default column names elsewhere. 
Answer: 

SELECT c.CompanyName, a.AddressLine1, a.City, 'Billing' AS AddressType 
FROM SalesLT.Customer AS c 
JOIN SalesLT.CustomerAddress AS ca 
ON ca.CustomerID = c.CustomerID 
JOIN SalesLT.Address AS a 
ON a.AddressID = ca.AddressID 
WHERE ca.AddressType = 'Main Office'; 

2- Adapt the query to retrieve the company name, first line of the street address, city, and a column named AddressType with the value 'Shipping' for customers where the address type in the SalesLT.CustomerAddress table is 'Shipping'. Make sure to use the aliases provided, and default column names elsewhere. 
Answer: 

SELECT c.CompanyName, a.AddressLine1, a.City, 'Shipping' AS AddressType 
FROM SalesLT.Customer AS c 
JOIN SalesLT.CustomerAddress AS ca 
ON c.CustomerID = ca.CustomerID 
JOIN SalesLT.Address AS a 
ON ca.AddressID = a.AddressID 
WHERE ca.AddressType = 'Shipping'; 

3- Use UNION ALL to combine the results returned by the two queries to create a list of all customer addresses that is sorted by company name and then address type. 
Answer: 

SELECT c.CompanyName, a.AddressLine1, a.City, 'Billing' AS AddressType 
FROM SalesLT.Customer AS c 
JOIN SalesLT.CustomerAddress AS ca 
ON c.CustomerID = ca.CustomerID 
JOIN SalesLT.Address AS a 
ON ca.AddressID = a.AddressID 
WHERE ca.AddressType = 'Main Office' 
UNION ALL 
SELECT c.CompanyName, a.AddressLine1, a.City, 'Shipping' AS AddressType 
FROM SalesLT.Customer AS c 
JOIN SalesLT.CustomerAddress AS ca 
ON c.CustomerID = ca.CustomerID 
JOIN SalesLT.Address AS a 
ON ca.AddressID = a.AddressID 
WHERE ca.AddressType = 'Shipping' 
ORDER BY c.CompanyName, AddressType; 

 

4- Write a query that returns the company name of each company that appears in a table of customers with a 'Main Office' address, but not in a table of customers with a 'Shipping' address. 
Answer: 

SELECT c.CompanyName 
FROM SalesLT.Customer AS c 
JOIN SalesLT.CustomerAddress AS ca 
ON c.CustomerID = ca.CustomerID 
JOIN SalesLT.Address AS a 
ON ca.AddressID = a.AddressID 
WHERE ca.AddressType = 'Main Office' 
EXCEPT 
SELECT c.CompanyName 
FROM SalesLT.Customer AS c 
JOIN SalesLT.CustomerAddress AS ca 
ON ca.CustomerID = c.CustomerID 
JOIN SalesLT.Address AS a 
ON ca.AddressID = a.AddressID 
WHERE ca.AddressType = 'Shipping' 
ORDER BY c.CompanyName; 

5- Write a query that returns the company name of each company that appears in a table of customers with a 'Main Office' address, and also in a table of customers with a 'Shipping' address. Make sure to use the aliases provided, and default column names elsewhere. 
Answer: 

SELECT c.CompanyName 
FROM SalesLT.Customer AS c 
JOIN SalesLT.CustomerAddress AS ca 
ON ca.CustomerID = c.CustomerID 
JOIN SalesLT.Address AS a 
ON ca.AddressID = a.AddressID 
WHERE ca.AddressType = 'Main Office' 
INTERSECT 
SELECT c.CompanyName 
FROM SalesLT.Customer AS c 
JOIN SalesLT.CustomerAddress AS ca 
ON c.CustomerID = ca.CustomerID 
JOIN SalesLT.Address AS a 
ON ca.AddressID = a.AddressID 
WHERE ca.AddressType = 'Shipping' 
ORDER BY c.CompanyName; 