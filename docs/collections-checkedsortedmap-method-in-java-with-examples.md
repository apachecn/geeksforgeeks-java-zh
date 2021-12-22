# Java 中的 Collections checkedSortedMap()方法，带示例

> 原文:[https://www . geesforgeks . org/collections-checked sortedmap-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collections-checkedsortedmap-method-in-java-with-examples/)

**java.util.Collections** 类的 **checkedSortedMap()** 方法用于返回指定排序地图的动态类型安全视图。
如果指定的映射是可序列化的，则返回的映射将是可序列化的。
因为 null 被认为是任何引用类型的值，所以返回的映射允许在后备映射插入 null 键或值时插入。
**语法:**

```java
public static  SortedMap
 checkedSortedMap(SortedMap m, Class keyType, Class valueType)
```

**参数:**该方法将以下参数作为参数

*   **m–**为其返回动态类型安全视图的地图
*   **钥匙类型–**允许 m 持有的钥匙类型
*   **值类型–**允许 m 持有的值类型

**返回值:**该方法动态返回指定地图的**类型安全视图**。
以下举例说明 *checkedSortedMap()* 方法
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// checkedSortedMap() method
// for <String, String> type

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {
        try {

            // creating object of SortedMap<String, String>
            SortedMap<String, String>
                smap = new TreeMap<String, String>();

            // Adding element to smap
            smap.put("Ram", "Gopal");
            smap.put("Karan", "Arjun");
            smap.put("Karn", "Veer");

            // printing the sorted map
            System.out.println("Sorted map:\n"
                               + smap);

            // create typesafe view of the specified map
            SortedMap<String, String>
                tsmap = Collections
                            .checkedSortedMap(smap,

<strong>Output:</strong>
<pre>{Karan=39, Karn=40, Ram=20}</pre>
                                              String.class,
                                              String.class);

            // printing the typesafe view of specified sorted map
            System.out.println("Typesafe view of sorted map:\n"
                               + tsmap);
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
Sorted map:
{Karan=Arjun, Karn=Veer, Ram=Gopal}
Typesafe view of sorted map:
{Karan=Arjun, Karn=Veer, Ram=Gopal}
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// checkedSortedMap() method
// for <String, Integer> type

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // creating object of SortedMap<String, Integer>
            SortedMap<String, Integer> smap = new TreeMap<String, Integer>();

            // Adding element to smap
            smap.put("Ram", 20);
            smap.put("Karan", 39);
            smap.put("Karn", 40);
            // printing the sorted map
            System.out.println("Sorted map:\n"
                               + smap);

            // create typesafe view of the specified map
            SortedMap<String, Integer>
                tsmap = Collections
                            .checkedSortedMap(smap,
                                              String.class,
                                              Integer.class);

            // printing the typesafe view of specified sorted map
            System.out.println("Typesafe view of sorted map:\n"
                               + tsmap);
        }
        catch (IllegalArgumentException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
Sorted map:
{Karan=39, Karn=40, Ram=20}
Typesafe view of sorted map:
{Karan=39, Karn=40, Ram=20}
```