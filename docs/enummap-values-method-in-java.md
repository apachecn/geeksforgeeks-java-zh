# Java 中的枚举值()方法

> 原文:[https://www . geesforgeks . org/enummap-values-method-in-Java/](https://www.geeksforgeeks.org/enummap-values-method-in-java/)

Java 中的 Java.util.EnumMap.values()方法用于从映射的值中创建一个集合。它基本上返回枚举中值的集合视图。

**语法:**

```java
EnumMap.values()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回映射值的集合视图。

以下程序说明了函数的工作原理:
**程序 1:**

```java
// Java program to demonstrate values()
import java.util.*;

// An enum of geeksforgeeks
public enum gfg {
    India_today,
    United_States_today
}
;

class Enum_demo {
    public static void main(String[] args)
    {

        EnumMap<gfg, Integer> mp = new 
                        EnumMap<gfg, Integer>(gfg.class);

        // Values are associated
        mp.put(gfg.India_today, 69);
        mp.put(gfg.United_States_today, 1073);

        // Prints the map
        System.out.println("The EnumMap: " + mp);

        // Retrieving the collection view of the map
        Collection<Integer> view = mp.values();

        // Prints the result
        System.out.println("Collection view of map: " + view);
    }
}
```

**Output:**

```java
The EnumMap: {India_today=69, United_States_today=1073}
Collection view of map: [69, 1073]

```

**程序 2:**

```java
// Java program to demonstrate the working of values()
import java.util.*;

// An enum of geeksforgeeks
public enum gfg {
    India_today,
    United_States_today,
    Canada_today
}
;

class Enum_demo {
    public static void main(String[] args)
    {
        EnumMap<gfg, Integer> mp = new 
                      EnumMap<gfg, Integer>(gfg.class);

        // Values are associated
        mp.put(gfg.India_today, 69);
        mp.put(gfg.United_States_today, 1073);
        mp.put(gfg.Canada_today, 1837);

        // Prints the map
        System.out.println("The EnumMap: " + mp);

        // Retrieving the collection view of the map
        Collection<Integer> view = mp.values();

        // Prints the result
        System.out.println("Collection view of map: " + view);
    }
}
```

**Output:**

```java
The EnumMap: {India_today=69, United_States_today=1073, Canada_today=1837}
Collection view of map: [69, 1073, 1837]

```