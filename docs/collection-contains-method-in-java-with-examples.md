# 集合包含 Java 中的()方法，示例

> 原文:[https://www . geesforgeks . org/collection-contains-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collection-contains-method-in-java-with-examples/)

**java.util.Collection 接口**的**包含(Object element)** 用于检查该集合中是否存在元素‘element’。此方法返回一个描述元素存在的布尔值。如果元素存在，则返回 true，否则返回 false。

**语法:**

```java
Collection.contains(Object element)

```

**参数:**该方法接受一个强制参数**元素**，类型为对象，将在该集合中进行检查。

**返回值:**这个方法返回一个**布尔值**，描述元素的存在。如果添加了元素，它将返回 true，否则将返回 false。

**异常:**此方法抛出以下异常:

*   **ClasscasteException:** If the class of the specified element prevents it from being added to this collection.
*   [T0】 NullPointerException: 【T1] If the specified element is empty and this collection does not allow empty elements.

以下示例说明了 Collection contains()方法:

**示例 1:** 使用链接列表类

```java
// Java code to illustrate boolean contains() method

import java.io.*;
import java.util.*;

public class GFG {
    public static void main(String args[])
    {

        // creating an empty LinkedList
        Collection<String> list = new LinkedList<String>();

        // use add() method to add elements in the list
        list.add("Geeks");
        list.add("for");
        list.add("Geeks");

        // Output the present list
        System.out.println("The list is: " + list);

        // Checking the presence of Geeks
        // using contains() method
        boolean result = list.contains("Geeks");

        // printing the result
        System.out.println("Is Geeks present in the List: "
                           + result);
    }
}
```

**输出:**

```java
The list is: [Geeks, for, Geeks]
Is Geeks present in the List: true

```

**例 2:** 使用 ArrayDeque 类

```java
// Java code to illustrate contains() method

import java.util.*;

public class ArrayDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ArrayDeque
        Collection<String> de_que = new ArrayDeque<String>();

        // Use add() method to add elements into the Deque
        de_que.add("Welcome");
        de_que.add("To");
        de_que.add("Geeks");
        de_que.add("4");
        de_que.add("Geeks");

        // Displaying the ArrayDeque
        System.out.println("ArrayDeque: " + de_que);

        // Checking the presence of Geeks
        // using contains() method
        boolean result = de_que.contains("Geeks");

        // printing the result
        System.out.println("Is Geeks present in the ArrayDeque: "
                           + result);
    }
}
```

**输出:**

```java
ArrayDeque: [Welcome, To, Geeks, 4, Geeks]
Is Geeks present in the ArrayDeque: true

```

**示例 3:** 使用数组列表类

```java
// Java code to illustrate contains() method

import java.io.*;
import java.util.*;

public class ArrayListDemo {
    public static void main(String[] args)
    {

        // create an empty array list with an initial capacity
        Collection<Integer> arrlist = new ArrayList<Integer>(5);

        // use add() method to add elements in the list
        arrlist.add(15);
        arrlist.add(20);
        arrlist.add(25);

        // Output the present list
        System.out.println("ArrayList: " + arrlist);

        // Checking the presence of 20
        // using contains() method
        boolean result = arrlist.contains(20);

        // printing the result
        System.out.println("Is 20 present in the ArrayList: "
                           + result);
    }
}
```

**输出:**

```java
ArrayList: [15, 20, 25]
Is 20 present in the ArrayList: true

```

**示例 4:** 演示空指针异常

```java
// Java code to illustrate boolean contains()

import java.util.*;

public class LinkedListDemo {
    public static void main(String args[])
    {

        // Creating an empty ArrayList
        Collection<String>
            list = new ArrayList<String>();

        // Displaying the list
        System.out.println("The ArrayList is: " + list);

        try {
            // Checking presence of null
            list.contains(null);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```java
The ArrayList is: []

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/collection . html # contains-Java . lang . object-](https://docs.oracle.com/javase/9/docs/api/java/util/Collection.html#contains-java.lang.Object-)