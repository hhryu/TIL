## How to use the Gson with kotlin

#### 1. Add dependency

- with Gradle/Android

```
dependencies {
	implementation 'com.google.code.gson:gson:2.8.5'
}
```

- with Maven

```xml
<dependencies>
    <!-- Gson: Java to Json conversion -->
    <dependency>
        <groupId>com.google.code.gson</groupId>
        <artifactId>gson</artifactId>
        <version>2.8.5</version>
        <scope>compile</scope>
    </dependency>
</dependencies>
```



#### 2. Primitives Examples

```kotlin
// Serialization
val gson = Gson()
gson.toJson(1)
gson.toJson("abcd")
val arry = intArrayOf(1, 2, 3, 4)
gson.toJson(arry)

// Deserialization
val one = gson.fromJson("1", Int::class.java)
val str = gson.fromJson("abcd", String::class.java)
val isTrue = gson.fromJson("True", Boolean::class.java)
```

