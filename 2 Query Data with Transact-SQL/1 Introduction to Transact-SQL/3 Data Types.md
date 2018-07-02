# Data Types

The importance of data types in this case, is that you must know what kind of data type you are getting if one of your needs is to combine data. In this table you can see the data types you can work with:

| Exact Numeric   | Aproximate Numeric|Characte|Date/Time       |Binary     |Other             |
| :---:           | :---:             | :---:  | :---:          | :---:     | :---:            |
| tinyint         | float             |char    |date            |binary     |cursor            |
| smallint  	  | real              |varchar |time            |varbinary  |hierarchyid       |
| int  	          |                   |text    |datetime        |image      |sql_variant       |
| bigint 	      |                   |nchar   |datetime2       |           |table             |
| bit  	          |                   |ntext   |smalldatetime   |           |timestamp         |
| decimal/numeric |                   |        |datetimeoffset  |           |uniqueidentifier  |
| money 	      |                   |        |                |           |xml               |
| small money 	  |                   |        |                |           |geography         |
| numeric    	  |                   |        |                |           |geometry          |

## Exact Numeric

They may all see the same but it is important if needed an specific. It is important to be accurate.

## Character

In a quick way, a character could be any alphanumerical character, and varchar is a chain of characaters. Little detail, when you see an **n** is to assign 2 bytes. This is for characters that may not use the alphanumerical characters.

## Date Time

This reviews all about date and time, the only thing that it changes is the accuracy.

# Data Type Conversion

This are the types of conversion you may need to do when working with data:

## Implicit Conversion
- Compatible data types can be automatically converted.

## Explicit Conversion
- Requires an explicit conversion function
    - CAST/ TRY_CAST
    - CONVERT/ TRY_CONVERT
    - PARSE/ TRY_PARSE
    - STR

# Examples of Conversion

## CAST

SELECT **CAST**(ProductID AS varchar(5)) + ':' + Name AS ProductName 
FROM SalesLT.Product;

## Convert

SELECT **CONVERT**(varchar(5), ProductID) + ':' + Name AS ProductName
FROM SalesLT.Product;

## Convert dates

SELECT SellStartDate, **CONVERT**(NVCHAR(30), SellStartDate) AS ConvertedDate, **CONVERT**(NVACHAR(30), SellStartDate, 126) AS ISO8601FormatDate
FROM SalesLT.Product;

