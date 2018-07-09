## SQL Date

#### 1. MSSQl format

- **DATE : YYYY-MM-DD**
- **DATETIME : YYYY-MM-DD HH:MI:SS**
- SMALLDATETIME : YYYY-MM-DD HH:MI:SS
- TIMESTAMP : unique number



#### 2. MySQL format

- **DATE : YYYY-MM-DD**
- **DATETIME : YYYY-MM-DD HH:MI:SS**
- TIMESTAMP : YYYY-MM-DD HH:MI:SS
- YEAR : YYYY or YY



| OrderID | ProductName | OrderDate  |    DateWithTime     |
| :-----: | :---------: | :--------: | :-----------------: |
|    1    |    Phone    | 2018-07-09 | 2018-07-09 23:20:11 |
|    2    |     Car     | 2018-07-07 | 2018-07-07 11:11:11 |
|    3    |    Book     | 2018-06-23 | 2018-06-23 15:30:24 |

- OrderDate : DATE / DateWithTime : DATETIME



```sql
SELECT ProductName FROM TABLE_NAME WHERE OrderDate = '2018-07-09'
-- result => ProductName : Phone

SELECT ProductName FROM TABLE_NAME WHERE DateWithTime = '2018-07-09'
-- reuslt => (X)
```
