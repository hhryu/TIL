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

