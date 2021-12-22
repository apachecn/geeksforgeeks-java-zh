# 用示例收集 Java 中的 isEmpty()方法

> 原文:[https://www . geesforgeks . org/collection-isempty-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collection-isempty-method-in-java-with-examples/)

**java.util.Collection 接口**的 **isEmpty()** 用于检查调用它的 Collection 是否为空。此方法不接受任何参数，也不返回任何值。

**语法:**

```
Collection.isEmpty()

```

**参数:**此方法不接受任何参数

**返回值:**此方法不返回值。

以下示例说明了集合 isEmpty()方法:

**示例 1:** 使用链接列表类

```
// Java code to illustrate boolean isEmpty() method

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

        // Check if list is empty
        // using isEmpty() method
        System.out.println("Is the LinkedList empty: "
                           + list.isEmpty());

        // Clearing the LinkedList
        list.clear();

        // printing the new list
        System.out.println("The new List is: " + list);

        // Check if list is empty
        // using isEmpty() method
        System.out.println("Is the LinkedList empty: "
                           + list.isEmpty());
    }
}
```

**输出:**

```
The list is: [Geeks, for, Geeks]
Is the LinkedList empty: false
The new List is: []
Is the LinkedList empty: true

```

**例 2:** 使用 ArrayDeque 类

```
// Java code to illustrate isEmpty() method

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

        // Check if ArrayDeque is empty
        // using isEmpty() method
        System.out.println("Is the ArrayDeque empty: "
                           + de_que.isEmpty());

        // Clearing the ArrayDeque
        de_que.clear();

        // printing the new ArrayDeque
        System.out.println("The new ArrayDeque is: "
                           + de_que);

        // Check if ArrayDeque is empty
        // using isEmpty() method
        System.out.println("Is the ArrayDeque empty: "
                           + de_que.isEmpty());
    }
}
```

**输出:**

```
ArrayDeque: [Welcome, To, Geeks, 4, Geeks]
Is the ArrayDeque empty: false
The new ArrayDeque is: []
Is the ArrayDeque empty: true

```

**示例 3:** 使用数组列表类

```
// Java code to illustrate isEmpty() method

import java.io.*;
import java.util.*;

public class ArrayListDemo {
    public static void main(String[] args)
    {

        // create an empty array list with an initial capacity
        Collection<Integer>
            arrlist = new ArrayList<Integer>(5);

        // use add() method to add elements in the list
        arrlist.add(15);
        arrlist.add(20);
        arrlist.add(25);

        // prints all the elements available in list
        System.out.println("ArrayList: " + arrlist);

        // Check if list is empty
        // using isEmpty() method
        System.out.println("Is the ArrayList empty: "
                           + arrlist.isEmpty());

        // Clearing the ArrayList
        arrlist.clear();

        // printing the new ArrayList
        System.out.println("The new ArrayList is: "
                           + arrlist);

        // Check if ArrayList is empty
        // using isEmpty() method
        System.out.println("Is the ArrayList empty: "
                           + arrlist.isEmpty());
    }
}
```

**输出:**

```
ArrayList: [15, 20, 25]
Is the ArrayList empty: false
The new ArrayList is: []
Is the ArrayList empty: true

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/collection . html # isEmpty–](https://docs.oracle.com/javase/9/docs/api/java/util/Collection.html#isEmpty--)