## SQL UPDATE문

- 테이블에 이미 저장되어 있는 data를 변경하고자 할 때 사용.
- 조건에 해당하는 row의 data들을 변경.



#### 1. Syntax

```sql
UPDATE Table_name SET Column_name = value1, Column_name = value2 WHERE Condition;
```



#### 2. Example

* Table  : PERSONS

|  ID  | Name  |  City   |
| :--: | :---: | :-----: |
|  1   | Mark  |  Seoul  |
|  2   | David |  Busan  |
|  3   |  Sam  | Incheon |
|  4   | Harry |  Daegu  |
|  5   | Kevin |  Busan  |

- Syntax

```sql
SELECT Name, City FROM PERSONS WHERE ID > 2;
```

- Result

|  ID  | Name  | City  |
| :--: | :---: | :---: |
|  1   | Mark  | Seoul |
|  2   | David | Busan |
|  3   | Nancy | Jeju  |
|  4   | Harry | Daegu |
|  5   | Kevin | Busan |



#### 3. 주의사항

- 조건(WHERE절)을 사용하지 않으면 모든 row가 해당되므로 모든 data가 변경됨.