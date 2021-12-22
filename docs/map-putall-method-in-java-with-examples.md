# 用示例映射 Java 中的 putAll()方法

> 原文:[https://www . geesforgeks . org/map-putall-method-in-Java-with-examples/](https://www.geeksforgeeks.org/map-putall-method-in-java-with-examples/)

此方法用于将指定映射中的所有映射复制到此映射。

**语法:**

```java
void putAll(Map m)
```

**参数:**这个方法只有一个参数映射 m，它包含要复制到给定映射的键值映射。

**返回:**该方法返回与该键相关的前一个值(如果存在)，否则返回-1。

下面的程序展示了 int putAll()方法的实现。

**程序 1:**

```java
// Java code to show the implementation of
// putAll method in Map interface

import java.util.*;
public class GfG {

    // Driver code
    public static void main(String[] args)
    {

        // Initializing a Map of type HashMap
        Map<Integer, String> map = new HashMap<>();
        map.put(1, "One");
        map.put(3, "Three");
        map.put(5, "Five");
        map.put(7, "Seven");
        map.put(9, "Nine");
        System.out.println(map);

        Map<Integer, String> mp = new HashMap<>();
        mp.put(10, "Ten");
        mp.put(30, "Thirty");
        mp.put(50, "Fifty");

        map.putAll(mp);

        System.out.println(map);
    }
}
```

**Output:**

```java
{1=One, 3=Three, 5=Five, 7=Seven, 9=Nine}
{1=One, 50=Fifty, 3=Three, 5=Five, 7=Seven, 9=Nine, 10=Ten, 30=Thirty}

```

**程序 2:** 下面是展示 put()实现的代码。

```java
// Java code to show the implementation of
// putAll method in Map interface
import java.util.*;
public class GfG {

    // Driver code
    public static void main(String[] args)
    {

        // Initializing a Map of type HashMap
        Map<String, String> map = new HashMap<>();
        map.put("1", "One");
        map.put("3", "Three");
        map.put("5", "Five");
        map.put("7", "Seven");
        map.put("9", "Nine");
        System.out.println(map);

        Map<String, String> mp = new HashMap<>();
        mp.put("10", "Ten");
        mp.put("30", "Thirty");
        mp.put("50", "Fifty");

        map.putAll(mp);

        System.out.println(map);
    }
}
```

**Output:**

```java
{1=One, 3=Three, 5=Five, 7=Seven, 9=Nine}
{1=One, 3=Three, 5=Five, 7=Seven, 9=Nine, 50=Fifty, 30=Thirty, 10=Ten}

```

**参考:**
[甲骨文文档](https://docs.oracle.com/javase/7/docs/api/java/util/Map.html#put(K, %20V))