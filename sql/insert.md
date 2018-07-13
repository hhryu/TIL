## SQL INSERT문

- DB에 새로운 data를 저장하기 위해 사용.
- 새로운 row를 추가.

#### 1. Syntax

```sql
-- 방법 1
INSERT INTO table_name(column1, column2) VALUES(value1, value2);

-- 방법 2
INSERT INTO table_name VALUES(value1, value2, value3);
```



#### 2. Example

* Table  : PERSONS

|  ID  | Name  | City  |
| :--: | :---: | :---: |
|  1   | Mark  | Seoul |
|  2   | David | Busan |
|  3   |  Sam  | Busan |

##### 2-1) 모든 column의 data를 입력하는 경우

- Syntax

```sql
INSERT INTO PERSONS (ID, Name, City) VALUES (4, 'Nancy', 'Daegu');
```

- Result

|  ID  | Name  | City  |
| :--: | :---: | :---: |
|  1   | Mark  | Seoul |
|  2   | David | Busan |
|  3   |  Sam  | Busan |
|  4   | Nancy | Daegu |

##### 2-2) 일부 column의 data만 입력하는 경우

- Syntax

```sql
INSERT INTO PERSONS (Name, City) VALUES ('Mason', 'Jeju');
```

- Result

|  ID  | Name  | City  |
| :--: | :---: | :---: |
|  1   | Mark  | Seoul |
|  2   | David | Busan |
|  3   |  Sam  | Busan |
|  4   | Mason | Jeju  |

- 단, 생략된 column(ID)의 default값이 정해져 있는 경우만 가능하다.

  (예를 들면, Auto Increment / DEFAULT / Nullable인 경우)