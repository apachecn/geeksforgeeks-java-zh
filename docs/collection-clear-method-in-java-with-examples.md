# 用示例收集 Java 中的 clear()方法

> 原文:[https://www . geesforgeks . org/collection-clear-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collection-clear-method-in-java-with-examples/)

**java.util.Collection 接口**的 **clear()** 用于清除调用它的 Collection。此方法不接受任何参数，也不返回任何值。

**语法:**

```
Collection.clear()

```

**参数:**此方法不接受任何参数

**返回值:**此方法不返回值。

**异常:**此方法抛出以下异常:

*   **Operation exception is not supported:** If this collection does not support adding operation

以下示例说明了 Collection clear()方法:

**示例 1:** 使用链接列表类

```
// Java code to illustrate boolean clear() method

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

        // Clearing the LinkedList
        list.clear();

        // printing the new list
        System.out.println("The new List is: " + list);
    }
}
```

**输出:**

```
The list is: [Geeks, for, Geeks]
The new List is: []

```

**例 2:** 使用 ArrayDeque 类

```
// Java code to illustrate clear() method

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

        // Clearing the ArrayDeque
        de_que.clear();

        // printing the new ArrayDeque
        System.out.println("The new ArrayDeque is: "
                           + de_que);
    }
}
```

**输出:**

```
ArrayDeque: [Welcome, To, Geeks, 4, Geeks]
The new ArrayDeque is: []

```

**示例 3:** 使用数组列表类

```
// Java code to illustrate clear() method

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

        // prints all the elements available in list
        System.out.println("ArrayList: " + arrlist);

        // Clearing the ArrayList
        arrlist.clear();

        // printing the new ArrayList
        System.out.println("The new ArrayList is: "
                           + arrlist);
    }
}
```

**输出:**

```
ArrayList: [15, 20, 25]
The new ArrayList is: []

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/collection . html # clear–](https://docs.oracle.com/javase/9/docs/api/java/util/Collection.html#clear--)