# Laboratory 2 questions and answers

1- Finish the Transact-SQL query that retrieves all values for Cityand StateProvince, without duplicates, from the Addresstable. 
Answer: 

SELECT DISTINCT City, StateProvince 
FROM SalesLT.Address; 

2- Finish the query to retrieve the names of the top ten percent of products by weight. 
Answer: 

SELECT TOP 10 Percent Name 
FROM SalesLT.Product  
ORDER BY Weight DESC; 

3- Tweak the query to list the heaviest 100 products not including the ten most heavy ones. 
Answer: 

SELECT Name 
FROM SalesLT.Product 
ORDER BY Weight DESC OFFSET 10 ROWS FETCH NEXT 100 ROWS ONLY; 

4- Write a query to find the names, colors, and sizes of the products with a product model ID of 1. 
Answer: 

SELECT Name, Color, Size 
FROM SalesLT.Product WHERE ProductModelID = 1; 

5- Retrieve the product number and name of the products that have a Color of 'Black', 'Red', or 'White' and a Size of 'S' or 'M'. 
Answer: 

SELECT ProductNumber, Name 
FROM SalesLT.Product WHERE Color IN ('Black', 'Red', 'White') AND Size IN ('S', 'M'); 

6- Retrieve the product number, name, and list price of products that have a product number beginning with 'BK-'. 
Answer: 
SELECT ProductNumber, Name, ListPrice 
FROM SalesLT.Product WHERE ProductNumber Like 'BK%'; 

7- Modify your previous query to retrieve the product number, name, and list price of products with product number beginning with 'BK-' followed by any character other than 'R', and ending with a '-' followed by any two numerals. 
Remember: 
to match any string of zero or more characters, use % 
to match characters that are not R, use [^R] 
to match a numeral, use [0-9] 
Answer: 

SELECT ProductNumber, Name,ListPrice 
FROM SalesLT.Product WHERE ProductNumber LIKE 'BK-[^R]%-[0-9][0-9]'; 