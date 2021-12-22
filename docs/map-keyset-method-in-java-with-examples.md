# 用示例在 Java 中映射 keySet()方法

> 原文:[https://www . geesforgeks . org/map-key set-method-in-Java-with-examples/](https://www.geeksforgeeks.org/map-keyset-method-in-java-with-examples/)

此方法用于返回此地图中包含的键的集合视图。集合由地图支持，因此对地图的更改会反映在集合中，反之亦然。

**语法:**

```java
Set keySet()
```

**参数:**这个方法没有参数。

**返回:**该方法返回一个包含指定地图关键点的集合。

下面的程序展示了 int keySet()方法的实现。

**程序 1:**

```java
// Java code to show the implementation of
// isEmpty method in Map interface
import java.util.*;
public class GfG {

    // Driver code
    public static void main(String[] args)
    {

        // Initializing a Map of type HashMap
        Map<String, String> map = new HashMap<>();

        System.out.println(map);

        System.out.println(map.isEmpty());
    }
}
```

**输出:**

```java
{}
true

```

**程序 2:** 下面是展示 hashCode()实现的代码。

```java
// Java code to show the implementation of
// keySet method in Map interface
import java.util.*;
public class GfG {

    // Driver code
    public static void main(String[] args)
    {

        // Initializing a Map of type HashMap
        Map<Integer, String> map = new HashMap<>();
        Set<Integer> s = new HashSet<>();
        map.put(1, "One");
        map.put(3, "Three");
        map.put(5, "Five");
        map.put(7, "Seven");
        map.put(9, "Ninde");
        System.out.println(map);
        s = map.keySet();
        System.out.println(s);
    }
}
```

**输出:**

```java
{1=One, 3=Three, 5=Five, 7=Seven, 9=Ninde}
[1, 3, 5, 7, 9]

```

**参考:**
[甲骨文文档](https://docs.oracle.com/javase/7/docs/api/java/util/Map.html#keySet())