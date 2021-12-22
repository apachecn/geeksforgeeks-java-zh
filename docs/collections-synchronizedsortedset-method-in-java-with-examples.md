# Java 中的 Collections synchronized sorted set()方法，示例

> 原文:[https://www . geeksforgeeks . org/collections-synchronizedstoredset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collections-synchronizedsortedset-method-in-java-with-examples/)

**java.util.Collections** 类的 **synchronizedSortedSet()** 方法用于返回由指定排序集支持的同步(线程安全)排序集。为了保证串行访问，对后备排序集的所有访问都通过返回的排序集(或其视图)来完成是非常关键的。

**语法:**

```java
public static <T> SortedSet<T>
  synchronizedSortedSet(SortedSet<T> s)
```

**参数:**该方法将**排序集**作为参数“包装”在同步排序集中。

**返回值:**该方法返回指定排序集的**同步视图**。

下面是说明 synchronizedSortedSet()方法的示例

**例 1:**

```java
// Java program to demonstrate
// synchronizedSortedSet() method
// for <String> Value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // creating object of SortedSet<String>
            SortedSet<String> set = new TreeSet<String>();

            // populate the set
            set.add("A");
            set.add("B");
            set.add("C");
            set.add("D");

            // printing the Collection
            System.out.println("Sorted Set : " + set);

            // create a synchronized sorted set
            SortedSet<String>
                sorset = Collections
                             .synchronizedSortedSet(set);

            // printing the set
            System.out.println("Sorted set is : "
                               + sorset);
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
Sorted Set : [A, B, C, D]
Sorted set is : [A, B, C, D]

```

**例 2:**

```java
// Java program to demonstrate
// synchronizedSortedSet() method
// for <Integer> Value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // creating object of SortedSet<String>
            SortedSet<Integer>
                set = new TreeSet<Integer>();

            // populate the set
            set.add(10);
            set.add(20);
            set.add(30);
            set.add(40);

            // printing the Collection
            System.out.println("Sorted Set : " + set);

            // create a synchronized sorted set
            SortedSet<Integer>
                sorset = Collections
                             .synchronizedSortedSet(set);

            // printing the set
            System.out.println("Sorted set is : "
                               + sorset);
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
Sorted Set : [10, 20, 30, 40]
Sorted set is : [10, 20, 30, 40]

```