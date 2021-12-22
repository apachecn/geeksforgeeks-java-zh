# 用示例映射 Java 中的 hashCode()方法

> 原文:[https://www . geesforgeks . org/map-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/map-hashcode-method-in-java-with-examples/)

该方法用于为包含键和值的给定映射生成哈希代码。

**语法:**

```
int hashCode()
```

**参数:**这个方法没有参数。

**返回:**该方法返回给定地图的 hashCode 值。

下面的程序展示了 int hashCode()方法的实现。

**程序 1:**

```
// Java code to show the implementation of
// hashCode method in Map interface
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
        map.put(9, "Ninde");
        System.out.println(map);

        int hash = map.hashCode();

        System.out.println(hash);
    }
}
```

**Output:**

```
{1=One, 3=Three, 5=Five, 7=Seven, 9=Ninde}
238105666

```

**程序 2:** 下面是展示 hashCode()实现的代码。

```
// Java code to show the implementation of
// hashCode method in Map interface
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

        int hash = map.hashCode();

        System.out.println(hash);
    }
}
```

**Output:**

```
{1=One, 3=Three, 5=Five, 7=Seven, 9=Ninde}
238105618

```

**参考:**
[甲骨文文档](https://docs.oracle.com/javase/6/docs/api/java/util/ArrayList.html#contains(java.lang.Object))