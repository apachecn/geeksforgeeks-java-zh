# 将数组转换为 Java 中的链表

> 原文:[https://www . geesforgeks . org/convert-array-to-linked list-in-Java/](https://www.geeksforgeeks.org/convert-array-to-linkedlist-in-java/)

数组是连续的内存分配，而链表是随机放置在内存中的元素块，它们被链接在一起，其中一个块保存内存中另一个块的地址。有时根据需求或者因为内存中的空间问题，在进取世界中有更大的代码块，有必要将数组转换为列表。这里演示了数组到链表的转换。

**方法:**

1.  Use the [*aslist ()*](https://www.geeksforgeeks.org/arrays-aslist-method-in-java-with-examples/) method to collect classes.
2.  Use the [*addall ()*](https://www.geeksforgeeks.org/java-util-linkedlist-addall-method-in-java/) method to collect classes.

**方法 1:** 使用 [*作为*](https://www.geeksforgeeks.org/arrays-aslist-method-in-java-with-examples/) 方法的集合类

这个方法结合 Collection.toArray()充当基于数组和基于集合的 API 之间的桥梁。返回的列表被序列化并实现随机访问。这在 0(1)时间内运行。

**语法:**

```
public static List asList(T... a) ;
```

**参数:**该方法取需要转换为 List 的数组 a。这里，参数数组的工作方式类似于对象数组参数。

**进场:**

1.  Array.
2.  Convert an array to a list.
3.  Use the constructor to create a linked list from the list.

**示例**

## Java

```
// Java Program to convert Array to LinkedList

// Importing array, List & LinkedList classes from
// java.util package
import java.util.Arrays;
import java.util.LinkedList;
import java.util.List;

// Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Ccreate a string Array
        String[] strArr = { "A", "B", "C", "D", "E" };

        // Convert array to list
        List<String> list = Arrays.asList(strArr);

        // Create a LinkedList and
        // pass List in LinkedList constructor
        LinkedList<String> linkedList
            = new LinkedList<String>(list);

        // Display and print all elements of LinkedList
        System.out.println("LinkedList of above array : "
                           + linkedList);
    }
}
```

**输出**

```
LinkedList of above array : [A, B, C, D, E]
```

**方法 2:** 使用 [*addAll()*](https://www.geeksforgeeks.org/java-util-linkedlist-addall-method-in-java/) 方法的集合类

此方法用于将作为参数传递给此函数的集合中的所有元素追加到列表的末尾，记住集合迭代器的返回顺序。

**语法:**

```
*boolean* addAll(Collection C) ;
```

**参数:**参数 *C* 是数组列表的集合。它是需要在列表末尾追加元素的集合。

**返回值:**如果至少执行了一个追加操作，则该方法返回真，否则返回假。

**进场:**

1.  Array.
2.  Create an empty list of links.
3.  Use the *addall ()* method of the collections class with two objects as parameters.
    *   The first object to convert.
    *   The second object to be converted.

**示例**

## Java

```
// Java Program to convert Array to LinkedList

// Importing array, List & LinkedList, Collections classes
// from java.util package
import java.util.Arrays;
import java.util.Collections;
import java.util.LinkedList;
import java.util.List;

// Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Create an Array
        // here string type
        String[] strArr = { "G", "E", "E", "K", "S" };

        // Create an empty LinkedList
        LinkedList<String> linkedList
            = new LinkedList<String>();

        // Append all elements of array to linked list
        // using Collections.addAll() method
        Collections.addAll(linkedList, strArr);

        // Print the above LinkedList received
        System.out.println("Converted LinkeddList : "+linkedList);
    }
}
```

**输出**

```
Converted LinkeddList : [G, E, E, K, S]
```