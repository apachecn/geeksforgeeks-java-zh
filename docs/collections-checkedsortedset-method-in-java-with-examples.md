# Java 中的 Collections checkedSortedSet()方法，带示例

> 原文:[https://www . geesforgeks . org/collections-checked sorted set-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collections-checkedsortedset-method-in-java-with-examples/)

**java.util.Collections** 类的 **checkedSortedSet()** 方法用于返回指定排序集的动态类型安全视图。
如果指定的排序集是可序列化的，则返回的排序集将是可序列化的。
因为 null 被认为是任何引用类型的值，所以返回的排序集允许在支持排序集插入 null 元素时插入 null 元素。
**语法:**

```java
public static  SortedSet checkedSortedSet(SortedSet s, Class type)
```

**参数:**该方法以以下参数为参数:

*   **s–**为其返回动态类型安全视图的排序集
*   **类型–**允许持有的元素类型

**返回值:**该方法动态返回指定排序集的**类型安全视图**。
以下举例说明 *checkedSortedSet()* 方法
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// checkedSortedSet() method
// for String value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // creating object of SortedMap<String>
            SortedSet<String> sset = new TreeSet<String>();

            // Adding element to smap
            sset.add("Ram");
            sset.add("Gopal");
            sset.add("Verma");

            // printing the sorted set
            System.out.println("Sorted Set: " + sset);

            // create typesafe view of the specified set
            // using checkedSortedSet() method
            SortedSet<String>
                tsset = Collections
                            .checkedSortedSet(sset, String.class);

            // printing the typesafe view of specified set
            System.out.println("Typesafe view of sorted set: \n"
                               + tsset);
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
Sorted Set: [Gopal, Ram, Verma]
Typesafe view of sorted set: 
[Gopal, Ram, Verma]
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// checkedSortedSet() method
// for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // creating object of SortedSet<Integer>
            SortedSet<Integer> sset = new TreeSet<Integer>();

            // Adding element to smap
            sset.add(20);
            sset.add(30);
            sset.add(40);

            // printing the sorted set
            System.out.println("Sorted Set: " + sset);

            // create typesafe view of the specified set
            // using checkedSortedSet() method
            SortedSet<Integer> tsset = Collections.checkedSortedSet(sset, Integer.class);

            // printing the typesafe view of specified set
            System.out.println("Typesafe view of sorted set: \n"
                               + tsset);
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
Sorted Set: [20, 30, 40]
Typesafe view of sorted set: 
[20, 30, 40]
```