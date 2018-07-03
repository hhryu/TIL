## SQL FOREIGN KEY Statement

#### 1. FOREIGN KEY

- this statement is used to link two tables together.
- a foreign key is a field in one table that refers to the primary key in another table.
- the table containing the **foreign key** is called the **child table**.
- the table containing the **primary key** is called the **referenced or parent table**.



##### *table : Persons

| PersonID | LastName  | FirstName | Age  |
| :------: | :-------: | :-------: | :--: |
|    1     |  Hansen   |    Ola    |  30  |
|    2     | Svendson  |   Tove    |  23  |
|    3     | Pettersen |   Kari    |  20  |

##### *table : Orders

| OrderID | OrderNumber | PersonID |
| :-----: | :---------: | :------: |
|    1    |    77895    |    3     |
|    2    |    44678    |    3     |
|    3    |    22456    |    2     |
|    4    |    24562    |    1     |



#### 2. on CREATE TABLE

```sql
-- on single column
-- in MySQL
CREATE TABLE Orders(
	OrderID int NOT NULL,
    OrderNumber int NOT NULL,
    PersonID int,
    PRIMARY KEY(OrderID),
    FOREIGN KEY(PersonID) REFERENCES Persons(PersonID)
);

-- in MSSQL, Oracle
CREATE TABLE Orders(
	OrderID int NOT NULL PRIMARY KEY,
    OrderNumber int NOT NULL,
    PersonID int FOREIGN KEY REFERENCES Persons(PersonID)
);

-- on multiple columns
-- in MySQL, MSSQL and Oracle
CREATE TABLE Orders(
	ID int NOT NULL,
    OrderNumber int NOT NULL,
    PersonID int,
    PRIMARY KEY(OrderID),
    CONSTRAINT FK_PersonOrder FOREIGN KEY(PersonID)
    REFERENCES Persons(PersonID)
);
```



#### 3. on ALTER TABLE

```sql
-- on single column
-- in MySQL, MSSQL and Oracle
ALTER TABLE Orders ADD FOREIGN KEY(PersonID) REFERENCES Persons(PersonID);

-- on multiple columns
ALTER TABLE Orders ADD CONSTRAINT FK_PersonOrder
FOREIGN KEY(PersonID) REFERENCES Persons(PersonID);
```



#### 3. Drop the PRIMARY KEY

```sql
-- in MySQL
ALTER TABLE Orders DROP FOREIGN KEY FK_PersonOrder;

-- in MSSQL and Oracle
ALTER TABLE Orders DROP CONSTRAINT FK_PersonOrder;
```

