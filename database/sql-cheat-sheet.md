# Git Cheet Sheet

### ALTER table

```bash
ALTER TABLE table_name ADD column_name datatype;
```
It is used to add columns to a table in a database

### AND

```bash
SELECT column_name(s) FROM table_name WHERE column_1=value_1 AND column_2=value_2;
```
It is an operator that is used to combine two conditions

### AS

```bash
SELECT column_name AS 'Alias' FROM table_name;
```
It is an keyword in SQL that is used to rename a column or table using an alias name

### AVG

```bash
SELECT AVG(column_name) FROM table_name;
```
It is used to aggregate a numeric column and return its average

### BETWEEN

```bash
SELECT column_name(s) FROM table_name WHERE column_name BETWEEN value_1 AND value_2;
```
It is an operator used to filter the result within a certain range

### CASE

```bash
SELECT column_name, CASE WHEN condition THEN 'Result_1' WHEN condition THEN 'Result_2' ELSE 'Result_3' END FROM table_name;
```
It is a statement used to create different outputs inside a SELECT statement

### COUNT

```bash
SELECT COUNT(column_name) FROM table_name;
```
It is a function that takes the name of a column as argument and counts the number of rows when the column is not NULL

### Create TABLE

```bash
CREATE TABLE table_name(column_1 datatype, column_2 datatype, column_3 datatype);
```
It is used to create a new table in a database and specify the name of the table and columns inside it

### DELETE

```bash
DELETE FROM table_name WHERE some_column=some_value;
```
It is used to remove the rows from a table;

### GROUP BY

```bash
SELECT column_name, COUNT(*) FROM table_name GROUP_BY column_name;
```
It is an clause in SQL used for aggregate functions in collaboration with the SELECT statement

### HAVING

```bash
SELECT column_name, COUNT(*) FROM table_name GROUP BY column_name HAVING COUNT(*)>value;
```
It is used in SQL because the WHERE keyword cannot be used in aggregating functions

### INNER JOIN

```bash
SELECT column_name(s) FROM table_1 JOIN table_2 ON table_1.column_name = table2.column_name;
```
It is used to combine rows from different tables if the Join condition goes TRUE

### INSERT

```bash
INSERT INTO table_name(column_1, column_2, column_3) VALUES(value_1, value_2, value_3);
```
It is used to add new rows to a table

### IS NULL / IS NOT NULL

```bash
SELECT column_name(s) FROM table_name WHERE column_name IS NULL;
```
It is an opeator used with the WHERE clause to check for the empty values

### LIKE 

```bash
SELECT column_name(s) FROM table_name WHERE column_name LIKE pattern;
```
It is a special operator used with the WHERE clause to search for a specific pattern in a column

### LIMIT 

```bash
SELECT column_name(s) FROM table_name LIMIT number;
```
It is a clause to specify the maximum number of rows the result set must have

### MAX

```bash
SELECT MAX(column_name) FROM table_name;
```
It is a function that takes number of columns as an argument and return the largest value among them

### MIN

```bash
SELECT MIN(column_name) FROM table_name;
```
It is a function that takes number of columns as an argument and return the smallest value among them

### OR

```bash
SELECT column_name FROM table_name WHERE column_name=value_1 OR column_name=value_2;
```
It is an operator that is used to filter the result set to contain only the rows where either condition is TRUE

### ORDER BY

```bash
SELECT column_name FROM table_name ORDER BY column_name ASC|DESC;
```
It is a clause used to sort the result set by a particular column either numerically or alphabetically

### OUTER JOIN

```bash
SELECT column_name(s) FROM table_1 LEFT JOIN table_2 ON table_1.column_name=table_2.column_name;
```
It is used to combine rows from different tables even if the condition is NOT TRUE

### ROUND

```bash
SELECT ROUND(column_name, integer) FROM table_name;
```
It is a function that takes the column name and a integer as an argument, and rounds the values in a column to the number of a decimal places specified by an integer

### SELECT

```bash
SELECT column_name FROM table_name;
```
It is a statement that is used to fetch data from a database

### SELECT DISTINCT

```bash
SELECT DISTINCT column_name FROM table_name;
```
It is used to specify that the statement is a query which returns unique values in specified columns

### SUM

```bash
SELECT SUM(column_name) FROM table_name;
```
It is a function used to return sum of values from a particular column

### UPDATE

```bash
UPDATE table_name SET some_column=some_value WHERE some_column=some_value;
```
It is used to edit rows in a table

### WHERE

```bash
SELECT column_name(s) FROM table_name WHERE column_name operator value;
```
It is a clause used to filter the result set to include the rows which where the condition is TRUE

### WITH

```bash
WITH temporary_name AS (SELECT * FROM table_name)SELECT * FROM temporary_name WHERE column_name operator value;
```
It is used to storeh the result of a particular query in a temporary table using an alias

## JOIN
![Visual-Representation-of-SQL-Joins](img/Visual_SQL_JOINS_orig.jpg)
---
## Refer to
[IntelliPaat](https://intellipaat.com/blog/tutorial/sql-tutorial/sql-commands-cheat-sheet/)
[CodeProject](https://www.codeproject.com/Articles/33052/Visual-Representation-of-SQL-Joins)
