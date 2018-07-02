# What is Transact SQL

## SQL
First of all **SQL** is Structured Query Language it was developed by IBM in the 1970s and adopted as a standard by ANSI and ISO standard bodies. It is widely used in industry in data platforms. In this case **Transact SQL** is the implementation bult by Microsoft, it is refered as **T-SQL**. The syntax  is similar to the rest of the standards but it has some differences. 

SQL is a declarative, not a procedural. This mean you describe what you want, don't specify the steps. With SQL you work with multiple intances of objects, so as really good advice when you work with SQL write what you want as a result not how you want to get it.

## Relational Databases
Entities are represented as **relations**(tables), in which their attributes are represented as **domains** (columns). 
#### Sales
| Price   | Sales|
| :---:   | :---:|
| 37      | 2    |
| 34  	  | 23   |
| 55  	  | 45   |
| 80 	  | 50   |

In this table you can see the Table **Sales** and its domains which are **price and sales**.


About this databases, normally they are normalized and have relationships between tables through primary and foreign keys. The **primary key** is a unique key of that table used to relates to a **foreign key** which is a key to look for information in another table.

## Schema

Schemas are namespaces for database objects, this help us identify the Tables. 

Fully-qualified names:
[server_name][database_name][schema_name]object name

Rememeber that in Azure you can only work with one Data Base so if that is the case you don't need to write all of this down, but in the rest of the cases you should.

## SQL Statement Types

| Data Manipulation Language   | Data Definition Language|Data Control Language|
| :---:                         | :---:                     | :---:|
| SELECT                        | CREATE                    |GRANT|
| INSERT  	                    | ALTER                     |REVOKE|
| UPDATE  	                    | DROP                      |DENY|
| DELETE 	                    |                           ||