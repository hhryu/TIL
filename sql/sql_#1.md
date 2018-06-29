## SQL Statement #1

#### 1. CREATE

```sql
--how to create the db
CREATE DATABASE testDB;

--how to create the table
CREATE TABLE table_name;
```



#### 2. DROP

```sql
--how to drop the db
DROP DATABASE testDB;

--how to drop the table
DROP TABLE table_name;

--TRUNCATE Statement is used to delete the data inside a table, but not the table itself.
TRUNCATE TABLE table_name;
```



#### 3. ALTER

- The ALTER Statement is used to add, delete, or modify columns in an existing table.

```sql
--how to add the column in a table
ALTER TABLE table_name ADD column_name datatype;

--how to drop the column in a table
--(some systems may restrict this statement)
ALTER TABLE table_name DROP COLUMN column_name;

--how to modify the data type of a column
--in MSSQL
ALTER TABLE table_name ALTER COLUMN column_name datatype;
--in MYSQL
ALTER TABLE table_name MODIFY COLUMN column_name datatype;
--in Oracle
ALTER TABLE table_name MODIFY column_name datatype;

```
