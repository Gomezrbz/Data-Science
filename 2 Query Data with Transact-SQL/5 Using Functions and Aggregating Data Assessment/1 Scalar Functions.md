# Scalar Function

- Operate on elements from a sigle row as inputs, it returns a single value as output. 
- Can be used like expression in queries.
- Deterministic or non-dertiministic. (Changing through time)

| Function Category   |
| :---:               |
| Configuration       | 
| Conversation  	  | 
| Cursor  	          |
| Date and Time	      |
| Mathematical        |
| Metadata            |
| Security            |
| String              |
| System              |
| System Statistical  |
| Text and Image      |

### Examples

SELECT YEAR(SellStartDate)........
> Returns the year of the date.

SELECT DATENAME(mm,SellStartDate).......
> Returns the name of the month.

SELECT DATEDIFF(yy,SellStartDate, GETDATE())........
>Returns the difference of years between the date using it and the data ones.

SELECT UPPER(Name)............
>Return the values in Upper Case.

SELECT CONCAT(FirstName,LastName)....
>Return the value of the 2 values concatenated.

