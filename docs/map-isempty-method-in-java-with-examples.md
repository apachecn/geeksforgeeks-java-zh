# 用示例将 isEmpty()方法映射到 Java 中

> 原文:[https://www . geesforgeks . org/map-isempty-method-in-Java-with-examples/](https://www.geeksforgeeks.org/map-isempty-method-in-java-with-examples/)

此方法用于检查映射是否有任何键和值对的条目。如果不存在映射，则返回 true。

**语法:**

```java
boolean isEmpty()
```

**参数:**这个方法没有参数。

**返回:**如果映射不包含任何键值映射，则该方法返回真。

下面的程序展示了 int isEmpty()方法的实现。

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

**Output:**

```java
{}
true

```

**程序 2:** 下面是展示 hashCode()实现的代码。

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
        map.put("1", "One");
        map.put("3", "Three");
        map.put("5", "Five");
        map.put("7", "Seven");
        map.put("9", "Ninde");
        System.out.println(map);

        System.out.println(map.isEmpty());
    }
}
```

**Output:**

```java
{1=One, 3=Three, 5=Five, 7=Seven, 9=Ninde}
false

```

**参考:**
[甲骨文文档](https://docs.oracle.com/javase/6/docs/api/java/util/ArrayList.html#contains(java.lang.Object))