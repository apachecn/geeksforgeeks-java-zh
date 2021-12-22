# Java 中的地图移除()方法，示例

> 原文:[https://www . geesforgeks . org/map-remove-method-in-Java-with-examples/](https://www.geeksforgeeks.org/map-remove-method-in-java-with-examples/)

如果某个键存在于地图中，则此方法用于从此地图中移除该键的映射。

**语法:**

```java
V remove(Object key)
```

**参数:**此方法只有一个参数键，其映射将从映射中移除。
**返回:**该方法返回该映射先前与该键关联的值，如果该映射不包含该键的映射，则返回 null。
下面的程序展示了 int remove()方法的实现。
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to show the implementation of
// remove method in Map interface
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

        map.remove(3);

        System.out.println(map);

        // If it doesn't exists, returns
        // null and does not affects the map
        map.remove(2);

        System.out.println(map);
    }
}
```

**Output:** 

```java
{1=One, 3=Three, 5=Five, 7=Seven, 9=Nine}
{1=One, 5=Five, 7=Seven, 9=Nine}
{1=One, 5=Five, 7=Seven, 9=Nine}
```