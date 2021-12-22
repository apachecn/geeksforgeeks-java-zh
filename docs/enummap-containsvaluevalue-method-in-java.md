# 枚举包含 Java 中的 Value(value)方法

> 原文:[https://www . geesforgeks . org/enummap-contains value-method-in-Java/](https://www.geeksforgeeks.org/enummap-containsvaluevalue-method-in-java/)

Java 中的 Java . util . enummap . contains value(*value*)方法用于确定映射的一个或多个键是否与给定值相关联。它将该值作为参数，如果该值由枚举映射中的任何键映射，则返回真。

**语法:**

```java
boolean containsValue(*Object value*)
```

**参数:**该方法接受一个参数*值*，该值是指其映射将由任意键检查的值。

**返回值:**当一个或多个键映射到同一个值时返回真。

下面的程序说明了 containsValue()方法:

**程序 1:**

```java
// Java program to demonstrate containsValue() method
import java.util.*;

// An enum of gfg ranking is created
public enum rank_countries {
    India,
    United_States,
    China,
    Japan,
    Canada,
    Russia
};

class Enum_map {
    public static void main(String[] args)
    {

        EnumMap<rank_countries, Integer> mp = new 
        EnumMap<rank_countries,Integer>(rank_countries.class);

        // values are associated in mp
        mp.put(rank_countries.India, 72);
        mp.put(rank_countries.United_States, 1083);
        mp.put(rank_countries.China, 4632);
        mp.put(rank_countries.Japan, 6797);
        mp.put(rank_countries.Canada, 1820);

        // check if map contains mapping at specified key
        boolean ans = mp.containsValue(72);

        // prints the result
        System.out.println("Map contains 72: " + ans);
    }
}
```

**Output:**

```java
Map contains 72: true

```

**程序 2:**

```java
// Java program to demonstrate containsValue() method
import java.util.*;

// An enum of gfg ranking is created
public enum rank_countries {
    India,
    United_States,
    China,
    Japan,
    Canada,
    Russia
};

class Enum_map {
    public static void main(String[] args)
    {

        EnumMap<rank_countries, Integer> mp = new 
        EnumMap<rank_countries,Integer>(rank_countries.class);

        // values are associated in mp
        mp.put(rank_countries.India, 72);
        mp.put(rank_countries.United_States, 1083);
        mp.put(rank_countries.China, 4632);
        mp.put(rank_countries.Japan, 6797);
        mp.put(rank_countries.Canada, 1820);

        // check if map contains mapping at specified key
        boolean ans = mp.containsValue(2000);

        // prints the result
        System.out.println("Map contains 2000: " + ans);
    }
}
```

**Output:**

```java
Map contains 2000: false

```