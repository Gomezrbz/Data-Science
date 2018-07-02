# Laboratory 1 questions and answers

1- Familiarize yourself with the Customer table by writing a Transact-SQL query that retrieves all columns for all customers. 
Answer: 

**SELECT * from SalesLT.Customer**

2- Create a table that lists all customer contact names. The table should include the Title, FirstName, MiddleName, LastName and Suffix of all customers. 
Answer: 

 
**SELECT Title,FirstName, MiddleName, LastName, Suffix FROM SalesLT.Customer;**

3- Complete the query to list the following elements for all customers: 
- The salesperson 
- A column named CustomerName that displays how the customer contact should be greeted (e.g. "Mr Smith"). 
- The customer's phone number (Phone) 
- Don't forget to space out the contents of your CustomerNamecolumn with + ' ' + and use the alias provided. 
Answer: 

**SELECT SalesPerson, Title + ' ' + LastName AS CustomerName, Phone FROM SalesLT.Customer;** 

4- Provide a list of all customer companies in the format <Customer ID>: <Company Name> (e.g. 78: Preferred Bikes). You'll need to use both CAST() and VARCHAR in your solution. Don't forget to use the alias provided. 
Answer: 

**SELECT CAST(CustomerID AS VARCHAR) + ': ' + CompanyName AS CustomerCompany FROM SalesLT.Customer;**

5- The SalesLT.SalesOrderHeader table contains records of sales orders. You have been asked to retrieve data for a report that shows: 
- The sales order number and revision number in the format <Order Number> (<Revision>) (e.g. SO71774 (2)). 
- The order date converted to ANSI standard format yyyy.mm.dd (e.g. 2015.01.31). 102 is the standard 
Answer:

**SELECT SalesOrderNumber + ' (' + STR(RevisionNumber, 1) + ')' AS OrderRevision, CONVERT(NVARCHAR(30),OrderDate, 102) AS OrderDate FROM SalesLT.SalesOrderHeader;** 

6- In this exercise, you'll write a query that returns a list of customer names. 
The list should consist of a single field in the format: 
<first name> <last name> (e.g. Keith Harris) if the middle name is unknown, 
<first name> <middle name> <last name> (e.g. Jane M. Gates) if a middle name is stored in the database. 
Answer:

**SELECT FirstName + ' ' + ISNULL(MiddleName + ' ', '') + LastName AS CustomerName FROM SalesLT.Customer;** 

7- Customers may provide AdventureWorks with an email address, a phone number, or both. If an email address is available, then it should be used as the primary contact method; if not, then the phone number should be used. 

Here, you will write a query that returns a list of customer IDs in one column, and a second column named PrimaryContact that contains the email address if known, and otherwise the phone number. 

Note: In the sample data provided in AdventureWorksLT, there are no customer records without an email address. Therefore, to verify that your query works as expected, we have run the following UPDATE statement to remove some existing email addresses before you write your query. (Don't worry, you'll learn about UPDATE statements later in the course!) 

UPDATE SalesLT.CustomerSET EmailAddress = NULLWHERE CustomerID % 7 = 1; 
Answer:

**SELECT CustomerID, COALESCE(EmailAddress, Phone) AS PrimaryContact FROM SalesLT.Customer;** 

8- You have been asked to create a query that returns a list of sales order IDs and order dates with a column named ShippingStatus that contains the text "Shipped" for orders with a known ship date, and "Awaiting Shipment" for orders with no ship date. 

Note: In the sample data provided in AdventureWorksLT, there are no SalesOrderHeader records without a ship date. Therefore, to verify that your query works as expected, we have run the following UPDATE statement to remove some existing ship dates before you write your query. (Again, don't worry, you'll learn about UPDATE statements later in the course!) 

UPDATE SalesLT.SalesOrderHeaderSET ShipDate = NULLWHERE SalesOrderID > 71899; 
Answer:

**SELECT SalesOrderID, OrderDate, CASE WHEN ShipDate IS NULL THEN 'Awaiting Shipment'ELSE 'Shipped'END AS ShippingStatus FROM SalesLT.SalesOrderHeader;**