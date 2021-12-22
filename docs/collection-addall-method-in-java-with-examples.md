# Java 中的集合 addAll()方法，带示例

> 原文:[https://www . geesforgeks . org/collection-addall-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collection-addall-method-in-java-with-examples/)

**java.util.Collection 界面**的**addAll(Collection<e>Collection)</e>**用于将 Collection‘Collection’添加到该现有集合中。此方法返回一个描述操作成功与否的布尔值。如果添加了集合，则返回 true，否则返回 false。

**语法:**

```
Collection.addAll(Collection<E> collection)

```

**参数:**该方法接受一个强制参数**集合**类型的集合，该集合将被添加到该集合中。

**返回值:**这个方法返回一个**布尔值**，描述操作的成功。如果添加了集合，则返回 true，否则返回 false。

**异常:**如果此集合不支持添加操作

*   **ClasscasteException:** If the class of the specified element prevents it from being added to this collection.*   [T0】 pointerexception: 【T1] If the specified element is empty and empty elements are not allowed in this collection.*   **非法引数例外:***   [T0】 illegalstatexception: 【T1] If the element cannot be added at this time due to the insertion restriction

以下示例说明了 Collection addAll()方法:

**示例 1:** 使用链接列表类

```
// Java code to illustrate boolean addAll()

import java.util.*;
import java.util.*;

public class LinkedListDemo {
    public static void main(String args[])
    {

        // Creating an empty LinkedList
        Collection<String>
            list = new LinkedList<String>();

        // A collection is created
        Collection<String>
            collect = new LinkedList<String>();
        collect.add("A");
        collect.add("Computer");
        collect.add("Portal");
        collect.add("for");
        collect.add("Geeks");

        // Displaying the list
        System.out.println("The LinkedList is: " + list);

        // Appending the collection to the list
        list.addAll(collect);

        // displaying the modified LinkedList
        System.out.println("The new linked list is: "
                           + list);
    }
}
```

**输出:**

```
The LinkedList is: []
The new linked list is: [A, Computer, Portal, for, Geeks]

```

**例 2:** 使用 ArrayDeque 类

```
// Java code to illustrate addAll() method

import java.util.*;

public class ArrayDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ArrayDeque
        Collection<String>
            de_que = new ArrayDeque<String>();

        // Creating a new ArrayDeque
        Collection<String>
            deque = new ArrayDeque<String>();
        deque.add("Welcome");
        deque.add("To");
        deque.add("Geeks");
        deque.add("4");
        deque.add("Geeks");

        // Displaying the list
        System.out.println("The ArrayDeque is: " + de_que);

        // Appending the collection to the list
        de_que.addAll(deque);

        // displaying the modified ArrayDeque
        System.out.println("The new ArrayDeque is: "
                           + de_que);
    }
}
```

**输出:**

```
The ArrayDeque is: []
The new ArrayDeque is: [Welcome, To, Geeks, 4, Geeks]

```

**示例 3:** 使用数组列表类

```
// Java code to illustrate boolean addAll()

import java.util.*;

public class LinkedListDemo {
    public static void main(String args[])
    {

        // Creating an empty ArrayList
        Collection<String>
            list = new ArrayList<String>();

        // A collection is created
        Collection<String>
            collect = new ArrayList<String>();
        collect.add("A");
        collect.add("Computer");
        collect.add("Portal");
        collect.add("for");
        collect.add("Geeks");

        // Displaying the list
        System.out.println("The ArrayList is: " + list);

        // Appending the collection to the list
        list.addAll(collect);

        // displaying the modified ArrayList
        System.out.println("The new ArrayList is: "
                           + list);
    }
}
```

**输出:**

```
The ArrayList is: []
The new ArrayList is: [A, Computer, Portal, for, Geeks]

```

**示例 4:** 演示空指针异常

```
// Java code to illustrate boolean addAll()

import java.util.*;

public class LinkedListDemo {
    public static void main(String args[])
    {

        // Creating an empty ArrayList
        Collection<String>
            list = new ArrayList<String>();

        // A collection is created
        Collection<String> collect = null;

        // Displaying the list
        System.out.println("The ArrayList is: " + list);

        try {
            // Appending the collection to the list
            list.addAll(collect);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```
The ArrayList is: []
Exception: java.lang.NullPointerException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/collection . html # addAll-Java . util . collection-](https://docs.oracle.com/javase/9/docs/api/java/util/Collection.html#addAll-java.util.Collection-)