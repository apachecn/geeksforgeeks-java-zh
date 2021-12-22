# 用示例

链接 Java 中的 List removeLastOccurrence()方法

> 原文:[https://www . geeksforgeeks . org/linked list-removelastpoccurrence-method-in-Java-with-example/](https://www.geeksforgeeks.org/linkedlist-removelastoccurrence-method-in-java-with-example/)

**java . util . concurrent . linkedlist . removelastpoccurrence()**方法是 Java 中的一个内置方法，它接受一个参数并删除列表中该元素的最后一次出现。因此，如果该元素不在列表中，它将保持不变。

**语法:**

```java
public boolean removeLastOccurrence(Object o)
```

**参数:**该函数接受一个对象 **elem** 作为参数，该参数表示其最后一次出现在列表中的对象将被删除。

**返回值:**如果列表中存在**元素**，则函数返回*真*，否则返回*假*。

下面的程序说明了**removelastpoccurrence()**方法的使用:

```java
// Java program to demonstrate removeLastOccurrence()
// method of LinkedList

import java.util.*;

class LinkedListDemo {
    public static void main(String[] args)
    {
        LinkedList<String> list
            = new LinkedList<String>();

        list.add("GFG");
        list.add("Geeks");
        list.add("Gfg");
        list.add("gfg");
        list.add("Geeks");

        // Displaying the existing LinkedList
        System.out.println("LinkedList: "
                           + list);

        // Remove last occurrence of  element
        list.removeLastOccurrence("Geeks");

        System.out.println("Removed last occurrence"
                           + " of 'Geeks' from the list");

        // Displaying the modified LinkedList
        System.out.println("LinkedList: "
                           + list);
    }
}
```

**Output:**

```java
LinkedList: [GFG, Geeks, Gfg, gfg, Geeks]
Removed last occurrence of 'Geeks' from the list
LinkedList: [GFG, Geeks, Gfg, gfg]

```

**程序 2:**

```java
// Java program to demonstrate removeLastOccurrence()
// method of LinkedList

import java.util.*;

class LinkedListDemo {
    public static void main(String[] args)
    {
        LinkedList<Integer>
            list = new LinkedList<Integer>();

        list.add(12);
        list.add(280);
        list.add(12);
        list.add(1050);
        list.add(12);

        // Displaying the existing LinkedList
        System.out.println("LinkedList: "
                           + list);

        // Remove last occurrence of  element
        list.removeLastOccurrence(12);

        System.out.println("Removed last occurrence"
                           + " of '12' from the list");

        // Displaying the modified LinkedList
        System.out.println("LinkedList: "
                           + list);
    }
}
```

**Output:**

```java
LinkedList: [12, 280, 12, 1050, 12]
Removed last occurrence of '12' from the list
LinkedList: [12, 280, 12, 1050]

```