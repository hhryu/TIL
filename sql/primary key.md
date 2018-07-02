## SQL PRIMARY KEY Statement

#### 1. PRIMARY KEY

- this statement uniquely identifies each record in a table.
- must contain UNIQUE values, and cannot contain NULL values.
- a table can have only one primary key.



#### 2. on CREATE TABLE

```sql
-- in MySQL
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    PRIMARY KEY(ID)
);

-- in MSSQL, Oracle
CREATE TABLE Persons(
    ID int NOT NULL PRIMARY KEY,
    LastName varchar(255),
    FirstName varchar(255),
    Age int
);

-- to define a PRIMARY KEY on multiple columns
-- in MySQL, MSSQL and Oracle
CREATE TABLE Persons(
	ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    CONSTRAINT PK_Person PRIMARY KEY(ID, LastName)
);
```



#### 3. on ALTER TABLE

```sql
-- in MySQL, MSSQL and Oracle
-- on single column
ALTER TABLE Persons ADD PRIMARY KEY(ID);

-- on multiple columns
ALTER TABLE Persons ADD CONSTRAINT PK_Person PRIMARY KEY(ID, LastName);
```



#### 3. Drop the PRIMARY KEY

```sql
-- in MySQL
ALTER TABLE Persons DROP PRIMARY KEY;

-- in MSSQL and Oracle
ALTER TABLE Persons DROP CONSTRAINT PK_Person;
```

