# Java 中的 NavigableMap lowerKey()方法

> 原文:[https://www . geesforgeks . org/naviglamblap-lowerkey-method-in-Java/](https://www.geeksforgeeks.org/navigablemap-lowerkey-method-in-java/)

导航映射接口的 **lowerKey()** 方法用于返回严格小于给定键的最大键，作为参数传递。更简单地说，这个方法用于在作为参数传递的元素之后查找下一个最大的元素。

**语法:**

```java
public K NavigableMap.lowerKey(K key)
```

**参数:**该方法取一个强制参数**键**，即这是要匹配的键。

**返回值:**这个方法返回**最大的键严格小于到键，**或者**空值**如果没有这样的键。

**异常:**该方法抛出以下异常:

*   **ClassCastException** :当指定的键无法与地图中可用的键进行比较时。
*   **NullPointRexception**:当映射中指定的键为空并且使用自然的
    排序时，这意味着比较器不允许空键。

下面的程序说明了 lowerKey()方法的使用:

**例 1:**

```java
// Java program to demonstrate lowerKey() method

import java.util.*;

public class FloorKeyDemo {
    public static void main(String args[])
    {

        // create an empty TreeMap
        NavigableMap<Integer, String>
            navMap = new TreeMap<Integer, String>();

        // Insert the values
        navMap.put(6, "Six");
        navMap.put(1, "One");
        navMap.put(5, "Five");
        navMap.put(3, "Three");
        navMap.put(8, "Eight");
        navMap.put(10, "Ten");

        // Print the Values of TreeMap
        System.out.println("TreeMap: " + navMap.toString());

        // Get the greatest key mapping of the Map

        // As here 9 is not available it returns 8
        // because 9 is strictly less than 11, present
        System.out.print("Lower Key Entry of Element 9 is: ");
        System.out.println(navMap.lowerKey(9));

        // Though, 3 is available in the Map
        // it returns 1 because this method returns
        // strictly less than key according to the specified key
        System.out.print("Lower Key Entry of Element 3 is: ");
        System.out.println(navMap.lowerKey(3));
    }
}
```

**Output:**

```java
TreeMap: {1=One, 3=Three, 5=Five, 6=Six, 8=Eight, 10=Ten}
Lower Key Entry of Element 9 is: 8
Lower Key Entry of Element 3 is: 1

```

**示例 2:** 演示空指针异常

```java
// Java program to demonstrate lowerKey() method

import java.util.*;

public class FloorKeyDemo {
    public static void main(String args[])
    {

        // create an empty TreeMap
        NavigableMap<Integer, String>
            navMap = new TreeMap<Integer, String>();

        // Insert the values
        navMap.put(6, "Six");
        navMap.put(1, "One");
        navMap.put(5, "Five");
        navMap.put(3, "Three");
        navMap.put(8, "Eight");
        navMap.put(10, "Ten");

        // Print the Values of TreeMap
        System.out.println("TreeMap: " + navMap.toString());

        try {
            // Passing null as parameter to lowerKey()
            // This will throw exception
            System.out.println(navMap.lowerKey(null));
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```java
TreeMap: {1=One, 3=Three, 5=Five, 6=Six, 8=Eight, 10=Ten}
Exception: java.lang.NullPointerException

```