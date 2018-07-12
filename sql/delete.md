## SQL DELETE문

- 테이블에 저장되어 있는 data를 삭제하기 위해 사용.

- 조건에 해당하는 row를 삭제.

  

#### 1. Syntax

```sql
DELETE FROM Table_name WHERE Condition;
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
DELETE FROM PERSONS WHERE Name = 'Sam';

-- for the result
SELECT *FROM PERSONS;
```

- Result

|  ID  | Name  | City  |
| :--: | :---: | :---: |
|  1   | Mark  | Seoul |
|  2   | David | Busan |
|  4   | Harry | Daegu |
|  5   | Kevin | Busan |



#### 3. 주의사항

- 조건(WHERE절)을 사용하지 않으면 모든 row가 해당되므로 테이블의 모든 data가 삭제됨.