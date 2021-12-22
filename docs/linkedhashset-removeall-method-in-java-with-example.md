# Java 中 LinkedHashSet removeAll()方法示例

> 原文:[https://www . geeksforgeeks . org/link edhashset-remove all-method-in-Java-with-example/](https://www.geeksforgeeks.org/linkedhashset-removeall-method-in-java-with-example/)

**java.util.LinkedHashSet** 类的 **removeAll()** 方法用于从此集合中移除指定集合中包含的所有元素。

**语法:**

```java
public boolean removeAll(Collection c)
```

**参数:**该方法将**集合 c** 作为包含要从该集合中移除的元素的参数。

**返回值:**如果该设置因调用而改变，则该方法返回**真**。

**异常:**如果该集合包含空元素，并且指定的集合不允许空元素(可选)，或者指定的集合为空，则该方法抛出**空指针异常**。

以下是说明 *removeAll()* 方法的示例。

**例 1:**

```java
// Java program to demonstrate
// removeAll() method for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {

        try {

            // Creating object of LinkedHashSet<Integer>
            LinkedHashSet<Integer>
                set1 = new LinkedHashSet<Integer>();

            // Populating set1
            set1.add(1);
            set1.add(2);
            set1.add(3);
            set1.add(4);
            set1.add(5);

            // print set1
            System.out.println("LinkedHashSet before "
                               + "removeAll() operation : "
                               + set1);

            // Creating another object of  LinkedHashSet<Integer>
            LinkedHashSet<Integer>
                set2 = new LinkedHashSet<Integer>();
            set2.add(1);
            set2.add(2);
            set2.add(3);

            // print set2
            System.out.println("Collection Elements"
                               + " to be removed : "
                               + set2);

            // Removing elements from set
            // specified in set2
            // using removeAll() method
            set1.removeAll(set2);

            // print set1
            System.out.println("LinkedHashSet after "
                               + "removeAll() operation : "
                               + set1);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
LinkedHashSet before removeAll() operation : [1, 2, 3, 4, 5]
Collection Elements to be removed : [1, 2, 3]
LinkedHashSet after removeAll() operation : [4, 5]

```

**示例 2:** 适用于*空指针异常*

```java
// Java program to demonstrate
// removeAll() method for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {

        try {

            // Creating object of LinkedHashSet<Integer>
            LinkedHashSet<Integer>
                set1 = new LinkedHashSet<Integer>();

            // Populating set1
            set1.add(1);
            set1.add(2);
            set1.add(3);
            set1.add(4);
            set1.add(5);

            // print set1
            System.out.println("LinkedHashSet before "
                               + "removeAll() operation : "
                               + set1);

            // Creating another object of  LinkedHashSet<Integer>
            LinkedHashSet<Integer>
                set2 = null;

            // print set2
            System.out.println("Collection Elements"
                               + " to be removed : "
                               + set2);

            System.out.println("\nTrying to pass "
                               + "null as a specified element\n");

            // Removing elements from set
            // specified in set2
            // using removeAll() method
            set1.removeAll(set2);

            // print set1
            System.out.println("LinkedHashSet after "
                               + "removeAll() operation : "
                               + set1);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
LinkedHashSet before removeAll() operation : [1, 2, 3, 4, 5]
Collection Elements to be removed : null

Trying to pass null as a specified element

Exception thrown : java.lang.NullPointerException

```