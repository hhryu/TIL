## SQL DEFAULT constraint

- this constraint is used to provide the default value for a column.



#### 1. on CREATE TABLE

```sql
-- in MySQL, MSSQL and Oracle
CREATE TABLE Persons(
	ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int, 
    City varchar(255) DEFAULT 'Seoul'
);

-- this can also be used to insert system values by using functions
CREATE TABLE Orders(
	ID int NOT NULL,
    OrderNumber int NOT NULL,
    OrderDate date DEFAULT GETDATE()
);
```



#### 2. on ALTER TABLE

```sql
-- in MySQL
ALTER TABLE Persons ALTER City SET DEFAULT 'Seoul';

-- in MSSQL
ALTER TABLE Persons ALTER COLUMN City SET DEFAULT 'Seoul';

-- in Oracle
ALTER TABLE Persons MODIFY City DEFAULT 'Seoul';
```



#### 3. Drop the DEFAULT constraint

```sql
-- in MySQL
ALTER TABLE Persons ALTER City DROP DEFAULT;

-- in MSSQL and Oracle
ALTER TABLE Persons ALTER COLUMN City DROP DEFAULT;
```

