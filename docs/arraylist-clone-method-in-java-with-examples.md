# Java 中的数组列表克隆()方法，示例

> 原文:[https://www . geesforgeks . org/ArrayList-clone-method-in-Java-with-examples/](https://www.geeksforgeeks.org/arraylist-clone-method-in-java-with-examples/)

Java.util.ArrayList 。clone()方法用于创建所述数组列表的[浅拷贝](https://en.wikipedia.org/wiki/Object_copying#Shallow_copy)。它只是创建了一个列表的副本。

**语法:**

```
ArrayList.clone()
```

**参数:**该方法不取任何参数。

**返回值:**该函数返回链表实例的副本。

下面的程序说明了 Java.util.ArrayList.clone()方法:

**例 1:**

```
// Java code to illustrate clone() method

import java.io.*;
import java.util.ArrayList;

public class ArrayListDemo {

    public static void main(String args[])
    {

        // Creating an empty ArrayList
        ArrayList<String> list
            = new ArrayList<String>();

        // Use add() method
        // to add elements in the list
        list.add("Geeks");
        list.add("for");
        list.add("Geeks");
        list.add("10");
        list.add("20");

        // Displaying the list
        System.out.println("First ArrayList: "
                           + list);

        // Creating another linked list and copying
        ArrayList sec_list = new ArrayList();
        sec_list = (ArrayList)list.clone();

        // Displaying the other linked list
        System.out.println("Second ArrayList is: "
                           + sec_list);
    }
}
```

**Output:**

```
First ArrayList: [Geeks, for, Geeks, 10, 20]
Second ArrayList is: [Geeks, for, Geeks, 10, 20]

```

**例 2:**

```
// Java code to illustrate clone() method

import java.io.*;
import java.util.ArrayList;

public class ArrayListDemo {

    public static void main(String args[])
    {

        // Creating an empty ArrayList
        ArrayList<Integer> list
            = new ArrayList<Integer>();

        // Use add() method
        // to add elements in the list
        list.add(10);
        list.add(20);
        list.add(30);
        list.add(40);
        list.add(50);

        // Displaying the list
        System.out.println("First ArrayList: "
                           + list);

        // Creating another linked list and copying
        ArrayList sec_list = new ArrayList();
        sec_list = (ArrayList)list.clone();

        // Displaying the other linked list
        System.out.println("Second ArrayList is: "
                           + sec_list);
    }
}
```

**Output:**

```
First ArrayList: [10, 20, 30, 40, 50]
Second ArrayList is: [10, 20, 30, 40, 50]

```