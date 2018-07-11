## SQL SELECT문

- DB에 저장된 Data를 보기 위한 구문.
- 한 테이블에서 특정 Column만을 볼 수도 있고 그 테이블 전체를 볼 수도 있다.


#### 1. Syntax

```sql
-- column1, column2만을 리턴
SELECT column1, column2 FROM table_nam;

-- table_name의 전체 column을 리턴
SELECT *FROM table_name;
```


#### 2. Example

* Table  : PERSONS

|  ID  | Name  | City  |
| :--: | :---: | :---: |
|  1   | Mark  | Seoul |
|  2   | David | Busan |
|  3   |  Sam  | Daegu |

##### 2-1) 특정 Column만 보고싶은 경우

- Syntax

```sql
SELECT Name, City FROM PERSONS;
```

- Result

| Name  | City  |
| :---: | :---: |
| Mark  | Seoul |
| David | Busan |
|  Sam  | Busan |

##### 2-2) 모든 Column을 보고싶은 경우

- Syntax

```sql
SELECT *FROM PERSONS;
```

- Result

|  ID  | Name  | City  |
| :--: | :---: | :---: |
|  1   | Mark  | Seoul |
|  2   | David | Busan |
|  3   |  Sam  | Busan |



#### 3. DISTINCT

- 중복된 값을 제외한 Data를 보고 싶을 때 사용



##### 3-1) Example

- Syntax

```sql
SELECT DISTINCT City FROM PERSONS
```

- Result

| City  |
| :---: |
| Seoul |
| Busan |

