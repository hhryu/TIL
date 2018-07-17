## SQL Join

- 2개 이상의 테이블의 rows를 결합하여 보고자 할 때 사용.



##### * Sample

- Table  : PERSONS_INFO1

|  ID  | Name  | City  |
| :--: | :---: | :---: |
|  1   | Mark  | Seoul |
|  2   | David | Busan |
|  3   |  Sam  | Busan |

- Table  : PERSONS_INFO2

|  ID  |    Contact    |    Job     |
| :--: | :-----------: | :--------: |
|  1   | 010-1111-1111 |  Student   |
|  3   | 010-3333-3333 |  Student   |
|  4   | 010-2222-2222 | Programmer |

- Table  : PERSONS_INFO3

|  ID  | Country | Age  |
| :--: | :-----: | :--: |
|  1   |  Korea  |  27  |
|  3   |   UK    |  17  |
|  5   | France  |  22  |



#### 1. Inner Join

- 두 테이블에서 기준으로 잡은 column의 값이 일치하는 rows를 보여준다.

![](C:\Users\hhryu\Documents\github_repo\sql\inner_join.png)

##### 1-1) 2개의 테이블 Join

- Syntax

```mssql
SELECT PERSONS_INFO1.ID, PERSONS_INFO1.Name, PERSONS_INFO2.Job FROM PERSONS_INFO1
INNER JOIN PERSONS_INFO2 ON PERSONS_INFO1.ID = PERSONS_INFO2.ID;
```

- Result

|  ID  | Name |   Job   |
| :--: | :--: | :-----: |
|  1   | Mark | Student |
|  3   | Sam  | Student |



##### 1-2) 3개의 테이블 Join

- Syntax

```mssql
SELECT PERSONS_INFO1.Name, PERSONS_INFO2.Job, PERSONS_INFO3.Country FROM PERSONS_INFO1
INNER JOIN PERSONS_INFO2 ON PERSONS_INFO1.ID = PERSONS_INFO2.ID
INNER JOIN PERSONS_INFO3 ON PERSONS_INFO2.ID = PERSONS_INFO3.ID;
```

- Result

| Name |   Job   | Country |
| :--: | :-----: | :-----: |
| Mark | Student |  Korea  |
| Sam  | Student |   UK    |



##### 2. Left Join

- 왼쪽 테이블(기준) + 오른쪽 테이블 (단, 오른쪽 테이블은 조건에 일치하지 않는 row의 값을 NULL로 표현)

![](C:\Users\hhryu\Documents\github_repo\sql\left_join.png)

- Syntax

```mssql
SELECT * FROM PERSONS_INFO1 LEFT JOIN PERSONS_INFO2 ON PERSONS_INFO1.ID = PERSONS_INFO2.ID;
```

- Result

|  ID  | Name  | City  |  ID  |    Contact    |   Job   |
| :--: | :---: | :---: | :--: | :-----------: | :-----: |
|  1   | Mark  | Seoul |  1   | 010-1111-1111 | Student |
|  2   | David | Busan | NULL |     NULL      |  NULL   |
|  3   |  Sam  | Busan |  3   | 010-3333-3333 | Student |



##### 3. Rigth Join

- 오른쪽 테이블(기준) + 왼쪽 테이블 (단, 왼쪽 테이블은 조건에 일치하지 않는 row의 값을 NULL로 표현)

![](C:\Users\hhryu\Documents\github_repo\sql\right_join.png)

- Syntax

```mssql
SELECT * FROM PERSONS_INFO1 RIGHT JOIN PERSONS_INFO2 ON PERSONS_INFO1.ID = PERSONS_INFO2.ID;
```

- Result

|  ID  | Name | City  |  ID  |    Contact    |    Job     |
| :--: | :--: | :---: | :--: | :-----------: | :--------: |
|  1   | Mark | Seoul |  1   | 010-1111-1111 |  Student   |
|  3   | Sam  | Busan |  3   | 010-3333-3333 |  Student   |
| NULL | NULL | NULL  |  4   | 010-2222-2222 | Programmer |



##### 4. Full Join

- 왼쪽 테이블(기준) + 오른쪽 테이블(단, 오른쪽 테이블은 조건에  일치하지 않는 row의 값을 NULL로 표현)
- 오른쪽 테이블(기준) + 왼쪽 테이블(단, 왼쪽테이블은 조건에  일치하지 않는 row의 값을 NULL로 표현)

![](C:\Users\hhryu\Documents\github_repo\sql\full_join.png)

- Syntax

```mssql
SELECT * FROM PERSONS_INFO1 FULL JOIN PERSONS_INFO2 ON PERSONS_INFO1.ID = PERSONS_INFO2.ID;
```

- Result

|  ID  | Name  | City  |  ID  |    Contact    |    Job     |
| :--: | :---: | :---: | :--: | :-----------: | :--------: |
|  1   | Mark  | Seoul | NULL |     NULL      |    NULL    |
|  2   | David | Busan | NULL |     NULL      |    NULL    |
|  3   |  Sam  | Busan | NULL |     NULL      |    NULL    |
| NULL | NULL  | NULL  |  1   | 010-1111-1111 |  Student   |
| NULL | NULL  | NULL  |  3   | 010-3333-3333 |  Student   |
| NULL | NULL  | NULL  |  4   | 010-2222-2222 | Programmer |

