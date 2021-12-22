# 枚举包含 Java 中的 Key()方法

> 原文:[https://www . geesforgeks . org/enummap-contains key-method-in-Java/](https://www.geeksforgeeks.org/enummap-containskey-method-in-java/)

Java . util . enummap . contains key(*key*)方法用于检查该映射中是否存在参数中提到的指定键。

**语法:**

```java
boolean containsKey(*Object key*)
```

**参数:**该方法接受一个参数*键*，该参数是指待验证的键。

**返回值:**如果枚举中存在*键*，则该方法返回真，否则返回假。

下面的程序说明了 containsKey()方法:
**程序 1:**

```java
// Java program to demonstrate containsKey() method
import java.util.*;

// An enum of gfg visitors is created
public enum gfg_visitors {
    India,
    United_States,
    China,
    Japan,
    Canada
};

class Enum_map {
    public static void main(String[] args)
    {

        EnumMap<gfg_visitors, String> mp = new 
        EnumMap<gfg_visitors, String>(gfg_visitors.class);

        // values are associated in mp
        mp.put(gfg_visitors.India, "61.4%");
        mp.put(gfg_visitors.United_States, "18.4%");
        mp.put(gfg_visitors.China, "2.5%");
        mp.put(gfg_visitors.Japan, "1.1%");
        mp.put(gfg_visitors.Canada, "1.1%");

        // Check if map contains gfg visitor from United_States
        boolean ans = mp.containsKey(gfg_visitors.United_States);

        // Prints the result
        System.out.println("gfg_visitors from United States: " + ans);
    }
}
```

**Output:**

```java
gfg_visitors from United States: true

```

**程序 2:**

```java
// Java program to demonstrate containsKey() method
import java.util.*;

// An enum of gfg visitors is created
public enum gfg_visitors {
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

        EnumMap<gfg_visitors, String> mp = new 
        EnumMap<gfg_visitors, String>(gfg_visitors.class);

        // values are associated in mp
        mp.put(gfg_visitors.India, "61.4%");
        mp.put(gfg_visitors.United_States, "18.4%");
        mp.put(gfg_visitors.China, "2.5%");
        mp.put(gfg_visitors.Japan, "1.1%");
        mp.put(gfg_visitors.Canada, "1.1%");

        // check if map contains gfg visitor from Russia
        boolean ans = mp.containsKey(gfg_visitors.Russia);

        // prints the result
        System.out.println("gfg_visitors from Russia: " + ans);
    }
}
```

**Output:**

```java
gfg_visitors from Russia: false

```