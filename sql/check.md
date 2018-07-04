## SQL CHECK constraint

- this constraint is used to **limit the value range** in a column

  

#### 1. on CREATE TABLE

```sql
-- in MySQL
CREATE TABLE Persons(
	ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    CHECK (Age > 19)
);

-- in MSSQL, Oracle
CREATE TABLE Persons(
	ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int, CHECK (Age > 19)
);

-- to define a CHECK constraint on multiple columns
-- in MySQL, MSSQL and Oracle
CREATE TABLE Persons(
	ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    City varchar(255),
    CONSTRAINT CHK_Person CHECK (Age > 19 AND City='Seoul')
);
```



#### 3. on ALTER TABLE

```sql
-- in MySQL, MSSQL and Oracle
-- on single column
ALTER TABLE Persons ADD CHECK (Age > 19);

-- on multiple columns
ALTER TABLE Persons ADD CONSTRAINT CHK_Persons CHECK (Age > 19 AND City='Seoul');
```



#### 3. Drop the CHECK constraint

```sql
-- in MySQL
ALTER TABLE Persons DROP CHECK CHK_Person;

-- in MSSQL and Oracle
ALTER TABLE Persons DROP CONSTARINT CHK_Person;
```

