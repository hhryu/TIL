## SQL #2

#### 1. Constraints

- are used to specify rules for the data in  a table.

- can be specified when the table is created with the CREATE TABLE statement
- can be specified after the table is created with the ALTER TABLE statement.

```sql
CREATE TABLE table_name(
	column1 datatype constraints,
    column2 datatype constraints,
);
```



#### 2. NOT NULL

- ensure that a column cannot have a NULL value.
- by default, a column can hold NULL values.

```sql
CREATE TABLE Person(
    ID int NOT NULL, 
    LastName varchar(255) NOT NULL,
    FirstName varchar(255) NOT NULL,
    Age int			--Age is Nullale
);
```



#### 3. UNIQUE

- ensure that all values in a column are different.
- can have many UNIQUE constraints per table.

##### 3-1) on CREATE TABLE

```sql
-- in MSSQL, Oracle
CREATE TABLE Persons(
	ID int NOT NULL UNIQUE,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255) NOT NULL,
    Age int
);

-- in MySQL
CREATE TABLE Persons(
	ID int NOT NULL,
    LastName varchar(255),
    FirstName varchar(255),
    Age int,
    UNIQUE (ID)
);

-- for a UNIQUE constraint on multiple columns
-- in MySQL, Oracle, MSSQL
CREATE TABLE PERSONS (
    ID int NOT NULL,
    LastName varchar(255),
    FirstName varchar(255),
    Age int,
    CONSTRANITS UC_Person UNIQUE (ID, LastName)
);
```

##### 3-2) on ALTER TABLE 

- can use this when tha table is already created

```sql
-- on a column
ALTER TABLE Persons ADD UNIQUE (ID);

-- on multiple columns
ALTER TABLE Persons ADD CONSTRAINT UC_Person UNIQUE (ID, LastName);
```

##### 3-3) Drop a UNIQUE constraint

```sql
-- in MySQL
ALTER TABLE Persons DROP UNIQUE UC_Person;

-- in MSSQL, Oracle
ALTER TABLE persons DROP CONSTRAINT UC_Person;
```
