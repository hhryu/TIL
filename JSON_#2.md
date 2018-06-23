## JSON(JavaScript Object Notation) #2

#### 1. Accessing Object Values

- can access the object values by using dot(.) or square bracket([]) notation.

```json
person = {"name":"Henry", "age":30, "phone":null};

//using dot notation
name = person.name;

//using square bracket
name = person["name"];
```



#### 2. Looping an object

- can loop through object properties or property values by using the for-in loop

```json
person = {"name":"Henry", "age":30, "phone":null};

for(p in person) {
    //property
    document.getElementById("demo").innerHTML += p;
    
    //property value
    document.getElementById("demo").innerHTML += person[p]
}
```



#### 3.Nested objects

```json
person = {
    "name":"henry",
    "age":30,
    "phones":{
        "phone1":"iphone",
        "phone2":"galaxy"
    }
}

//using dot notation
p = person.phones.phone1;

//using square bracket
p = person.phones["phone2"];
```



#### 4. Modify values

```json
//using dot notation
person.phones.phone1 = "galaxy";

//using square bracket
person.phones["phone2"] = "iphone";
```



#### 5. Delete object property

```json
delete person.phone.phone2;
```

