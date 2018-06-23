## JSON(JavaScript Object Notation)

#### 1. 정의

- 가독성이 좋은 경량의 DATA-교환 형식

  

#### 2. 특징 

- **Both XML and JSON**

  - Self describing (human readable)
  - Hierarchical (values within values)
  - can be parsed and used by lots of programming languages.
  - can be fetched with an XMLHttpRequest.

- **Not XML but JSON**

  - doesn't use end tag.

  - shorter

  - quicker to read and writh

  - can use arrays.

    

#### 3. Syntax Rules

- JSON syntax is a subset of the Javascript syntax.

  - Data is in **name/value pairs**.

  - Data is seperated by quatation marks(따옴표).

  - Curly braces{중괄호} hold objects.

  - Square brackets[대괄호] hold arrays.

    

#### 4. Data Types

- Valid Data Types
  - string / number / object / array / boolean / null
- Not valid Data Types
  - function / date / undefined

```json
{"name":"Henry"}		          //string

{"age":30}				            //number

{"isSuccessful":true}       	//boolean

{"phone":null}		          	//null

{
    "person":{"name":"Henry", "age":30, "city":"Seoul"}		//object
}

{
    "persons":["Henry", "Anna", "James"]		//array
}
```
