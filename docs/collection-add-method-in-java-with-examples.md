# Java 中的集合 add()方法，带示例

> 原文:[https://www . geesforgeks . org/collection-add-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collection-add-method-in-java-with-examples/)

**java.util.Collection 接口**的 **add(E 元素)**用于将元素‘element’添加到该集合中。此方法返回一个描述操作成功与否的布尔值。如果添加了元素，它将返回 true，否则将返回 false。

**语法:**

```
Collection.add(E element)
```

**参数:**该方法接受一个强制参数**元素**，类型为 E，将被添加到该集合中。

**返回值:**一个**布尔值**描述操作的成功。如果添加了元素，它将返回 true，否则将返回 false。

**异常:**如果此集合不支持添加操作

*   **ClasscasteException:** If the class of the specified element prevents it from being added to this collection.*   [T0】 NullPointerException: 【T1] If the specified element is empty and this collection does not allow empty elements.*   **This method throws the following five exceptions:

    *   **is being added to this collection**
    *   **IllegalStateException:** If the element** cannot be added at this time due to the insertion restriction.

现在我们将在不同的类上实现这个方法，因为当涉及到 java 编程时，它是一个非常重要和必要的方法，所以这里我们将对每个类强调如下:

*   链接列表 1860 年
*   ArrayDeque(阵列)
*   数组列表类
*   NullPointerException 被抛出

让我们通过干净的 java 示例在上面列出的所有 4 种情况下实现 add()方法，如下所示:

**示例 1:** LinkedList 类

T5】Java

```
// Java code to illustrate boolean add() method

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

        // Adding new elements to the end
        list.add("Last");
        list.add("Element");

        // printing the new list
        System.out.println("The new List is: " + list);
    }
}
```

**输出:**

```
The list is: [Geeks, for, Geeks]
The new List is: [Geeks, for, Geeks, Last, Element]
```

**例 2:** ArrayDeque 类

T5】Java

```
// Java code to illustrate add() method

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
    }
}
```

**输出:**

```
ArrayDeque: [Welcome, To, Geeks, 4, Geeks]
```

**示例 3:** 使用 ArrayList 类

T5】Java

```
// Java code to illustrate add() method

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
        for (Integer number : arrlist) {
            System.out.println("Number = " + number);
        }
    }
}
```

**输出:**

```
Number = 15
Number = 20
Number = 25
```

> 极客确实保持了一个绑定在特殊情况下会抛出 NullPointer 异常，如下例所示:

**例 4:**

## Java

```
// Java code to illustrate boolean add()
// Where NullPointerException is Thrown

// Importing required utility classes
import java.util.*;

// Main class
// LinkedListDemo
class GFG {

    // Main driver method
    public static void main(String args[])
    {

        // Creating an empty ArrayList of string type
        Collection<String> list = new ArrayList<String>();

        // Printing and displaying the Arraylist
        System.out.println("The ArrayList is: " + list);

        // Note: Here by now we have not added any element/s

        // Try block to check for exceptions
        try {

            // Appending the null to the list
            // using add() method
            list.add(null);
        }

        // Catch block to handle exceptions
        catch (Exception e) {

            // Display message when exceptions occurs
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```
The ArrayList is: []
```

**输出说明:**这里我们需要拿起来，因为我们只会收到一个 List。因此，最好记录 add()方法是否接受它是否需要支持 null。