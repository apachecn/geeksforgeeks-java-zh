# Java 中的 Map put()方法，示例

> 原文:[https://www . geesforgeks . org/map-put-method-in-Java-with-examples/](https://www.geeksforgeeks.org/map-put-method-in-java-with-examples/)

此方法用于将指定值与此映射中的指定键相关联。

**语法:**

```
V put(K key,
    V value)
```

**参数:**这个方法有两个参数，key 和 value，其中 key 是左边的参数，value 是映射中 key 的对应值。

**返回:**该方法返回与该键相关联的上一个值(如果存在)，否则返回-1。

下面的程序展示了 int put()方法的实现。

**程序 1:**

```
// Java code to show the implementation of
// put method in Map interface
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
    }
}
```

**Output:**

```
{1=One, 3=Three, 5=Five, 7=Seven, 9=Ninde}

```

**程序 2:** 下面是展示 put()实现的代码。

```
// Java code to show the implementation of
// put method in Map interface
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
    }
}
```

**Output:**

```
{1=One, 3=Three, 5=Five, 7=Seven, 9=Ninde}

```

**参考:**
[甲骨文文档](https://docs.oracle.com/javase/7/docs/api/java/util/Map.html#put(K, %20V))