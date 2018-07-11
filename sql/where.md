## SQL Where절

- 조건에 만족하는 Data를 보고싶을 때 사용.



#### 1. Syntax

```sql
SELECT *from table_name WHERE 조건;
```



#### 2. Example

* Table  : PERSONS

|  ID  | Name  | City  |
| :--: | :---: | :---: |
|  1   | Mark  | Seoul |
|  2   | David | Busan |
|  3   |  Sam  | Daegu |

- Syntax

```sql
SELECT Name, City FROM PERSONS WHERE ID > 1;
```

- Result

| Name  | City  |
| :---: | :---: |
| David | Busan |
|  Sam  | Busan |



- Syntax

```sql
SELECT *FROM PERSONS ID = 1;
```

- Result

|  ID  | Name | City  |
| :--: | :--: | :---: |
|  1   | Mark | Seoul |


