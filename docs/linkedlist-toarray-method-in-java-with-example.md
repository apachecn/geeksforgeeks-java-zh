# 用示例

链接 Java 中的 toArray()方法列表

> 原文:[https://www . geeksforgeeks . org/linked list-to array-method-in-Java-with-example/](https://www.geeksforgeeks.org/linkedlist-toarray-method-in-java-with-example/)

**1:使用 toArray()**

**Java . util . LinkedList . ToArray()**方法返回一个数组，该数组包含列表中所有元素的正确顺序，即从第一个到最后一个。创建新数组时，返回的数组将是安全的(因此会分配新内存)。因此调用者可以自由修改数组。它充当了基于数组和基于集合的 API 之间的桥梁。

**语法**

```java
public Object[] toArray()
```

**参数:**不取任何参数。

**返回值:**返回一个包含列表中所有元素的数组。

以下示例说明了 LinkedList.toArray()方法:

**例 1:**

```java
// Java Program Demonstrate toArray()
// method of LinkedList

import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of LinkedList
        LinkedList<Integer> list
            = new LinkedList<Integer>();

        // Add numbers to end of LinkedList
        list.add(7855642);
        list.add(35658786);
        list.add(5278367);
        list.add(74381793);

        System.out.println("LinkedList: "
                           + list);

        Object[] a = list.toArray();
        System.out.println("Returned Array: "
                           + Arrays.toString(a));
    }
}
```

**Output:**

```java
LinkedList: [7855642, 35658786, 5278367, 74381793]
Returned Array: [7855642, 35658786, 5278367, 74381793]

```

**2:使用 toArray(T[])**

Java 中**链接表类**的 **toArray(arr[])** 方法用于形成与链接表相同元素的数组。它以正确的顺序返回一个包含这个链表中所有元素的数组**；**返回数组的运行时类型是指定数组的运行时类型。如果链接列表适合指定的数组，它将在其中返回。否则，将使用指定数组的运行时类型和此链接列表的大小来分配新数组。
如果链接列表适合指定的数组，并且有空间可供使用(即数组中的元素比链接列表多)，则紧接在链接列表末尾的数组中的元素被设置为空。(只有当调用方知道链接列表不包含任何空元素时，这在确定链接列表的长度时才有用。)

```java
public <T> T[] toArray(T[] a)
```

**参数:**该方法接受一个参数 **arr[]** ，如果链表的元素足够大，那么这个参数就是要存储链表元素的数组；否则，将为此目的分配一个相同运行时类型的新数组。

**返回值:**该方法返回一个数组，该数组包含类似于链表的元素。

**异常:**该方法可能会引发两种类型的异常:

*   **arraystorexception**:当提到的数组属于不同类型，无法与链表中提到的元素进行比较时。
*   **NullPointerException** :如果数组为 Null，那么抛出这个异常。

下面的程序说明了 LinkedList.toArray(arr[])方法的工作原理。

**程序 1:** 当数组有链表那么大时

```java
// Java code to illustrate toArray(arr[])

import java.util.*;

public class LinkedListDemo {
    public static void main(String args[])
    {
        // Creating an empty LinkedList
        LinkedList<String> list
            = new LinkedList<String>();

        // Use add() method to add
        // elements into the LinkedList
        list.add("Welcome");
        list.add("To");
        list.add("Geeks");
        list.add("For");
        list.add("Geeks");

        // Displaying the LinkedList
        System.out.println("The LinkedList: "
                           + list);

        // Creating the array and using toArray()
        String[] arr = new String[5];
        arr = list.toArray(arr);

        // Displaying arr
        System.out.println("Returned Array: "
                           + Arrays.toString(arr));
    }
}
```

**Output:**

```java
The LinkedList: [Welcome, To, Geeks, For, Geeks]
Returned Array: [Welcome, To, Geeks, For, Geeks]

```