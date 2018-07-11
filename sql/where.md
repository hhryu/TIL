## SQL Where절

- 조건에 만족하는 Data를 보고싶을 때 사용.



#### 1. Syntax

```sql
SELECT *from table_name WHERE 조건;
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

| Name  |  City   |
| :---: | :-----: |
|  Sam  | Incheon |
| Harry |  Daegu  |
| Kevin |  Busan  |



- Syntax

```sql
SELECT *FROM PERSONS ID = 1;
```

- Result

|  ID  | Name | City  |
| :--: | :--: | :---: |
|  1   | Mark | Seoul |



#### 3. AND, OR, NOT 연산자 사용

##### 3-1) 한 가지 연산자만 사용

- syntax

```sql
SELECT *FROM PERSONS WHERE ID < 3 AND City = 'Busan';
```

- Result

|  ID  | Name  | City  |
| :--: | :---: | :---: |
|  2   | David | Busan |

- syntax

```sql
SELECT *FROM PERSONS WHERE NOT City = 'Busan';
```

- Result

|  ID  | Name  |  City   |
| :--: | :---: | :-----: |
|  1   | Mark  |  Seoul  |
|  3   |  Sam  | Incheon |
|  4   | Harry |  Daegu  |



##### 3-2) 여러 연산자를 복합하여 사용

- syntax

```sql
SELECT *FROM PERSONS WHERE ID > 2 AND (City = 'Busan' OR City = 'Daegu');
```

- Result

|  ID  | Name  | City  |
| :--: | :---: | :---: |
|  4   | Harry | Daegu |
|  5   | Kevin | Busan |

