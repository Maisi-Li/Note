
##Basic
```sql
CREATE DATABASE sample;
USE sample; 
--use is used to select database;
DROP DATABASE sample;
```
***

##Data type

**Integer**:
 bigint - 2^63, int - 2^31, smallint [-32768, 32768] = 2^15, 
tinyint[0, 255] = 2^8;

decimal(m,d) m: total digit, d: digit after dot
float(m,d)

**Character**:
char(n):max:255, fixed length - stored and retrived
varchar(n):max:65535, variable length

text: max:65535

blob - binary large object: store picture

***
##Constraints
Not Null/ Default/ Unique/ Primary Key(cannot null and must be unique)/ Foreign Key/ Check constrain

e.g:
```
City varchar(255) DEFAULT "NANNING", P_ID int NOT NULL,
CHECK(P_ID > 0)
CONSTRAINT check _person CHECK (P_ID>0 AND ....)
```
***
##Create table
```sql
CREATE TABLE sample (
	id int primary key,
	name varchar(30)
);
```
```
DESC table // describe the table structure 
```
***
##Create table from other tables 
```
CREATE TABLE sample_2 AS
SELECT  P_ID, name 
From sample_1
[Where conditions...]
```
***
##Insert into table 
```sql
INSERT INTO sample_2 (col1, col2, ...)
VALUES (val1, val2, ....)
FROM sample_1
```
OR
```sql
INSERT INTO sample_2 
VALUES (val1, val2, ...)
FROM sample_1
```
***
##Insert into table_1 from table_2
```sql
INSERT INTO table_1 (col1, col2, ...)
SELECT col3, col4
FROM table_2
[WHERE condition]
```
***
##Logical Operator

ALL, ANY / AND , OR / BETWEEN / IN / LIKE / IS NULL

LIKE: "p%" p + string "p-" one char "%hotmail%" bb@hotmail.com

**BETWEEN:**
```sql
SELECT FROM table_1
WHERE value BETWEEN a AND/OR b
```

**IN:**
```sql
SELECT FROM table_1
WHERE city IN ('Paris', 'London')
```

**ALL and ANY:**
```sql
SELECT FROM table_1
WHERE t1.col1 < ANY/ALL(select value FROM table_2)
```
***
##UPDATE and DELETE
**UPDATE:**
```sql
UPDATE table_1
SET age = 26
WHERE id = 1990;
```
**DELETE:**
```sql
DELETE FROM table 1
WHERE id = 12
```
***
##TOP(not mysql) & LIMIT
**TOP:**
```sql
SELECT TOP n
FROM table_1
[WHERE ...]
```
**LIMIT:**
```sql
SELETE col
FROM table 
[WHERE ...]
LIMIT n;
```
***
##ORDER
```sql
SELECT * 
FROM table
ORDER BY name [AES(default) / DESC]
```
> Written with [StackEdit](https://stackedit.io/).