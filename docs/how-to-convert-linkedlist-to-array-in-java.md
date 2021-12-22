# 如何在 Java 中将 LinkedList 转换为 Array？

> 原文:[https://www . geesforgeks . org/how-convert-linked list-to-array-in-Java/](https://www.geeksforgeeks.org/how-to-convert-linkedlist-to-array-in-java/)

给定一个 Java 中的链表，任务是将这个链表转换成数组。

**示例:**

```java
Input: LinkedList: ['G', 'e', 'e', 'k', 's'] 
Output: Array: ['G', 'e', 'e', 'k', 's'] 

Input: LinkedList: [1, 2, 3, 4, 5]
Output: Array: [1, 2, 3, 4, 5] 

```

**进场:**

1.  获取链接列表
2.  使用 toArray()方法将链接列表转换为对象数组。
3.  使用 [Arrays.copyOf()方法](https://www.geeksforgeeks.org/arrays-copyof-in-java-with-examples/)将对象数组转换为所需类型的数组。
4.  将打印返回阵列

下面是上述方法的实现:

```java
// Java program to convert
// LinkedList to Array

import java.util.*;

public class GFG {

    // Function to convert LinkedList to Array
    public static <T> Object[] convertLinkedListToArray(LinkedList<T> linkedList)
    {

        // Converting LinkedList to Array
        Object[] array = linkedList.toArray();

        return array;
    }

    public static void main(String args[])
    {
        // Creating linked list
        LinkedList<String>
            linkedList = new LinkedList<String>();

        // Adding elements to the linked list
        linkedList.add("G");
        linkedList.add("e");
        linkedList.add("e");
        linkedList.add("k");
        linkedList.add("s");

        // Print the LinkedList
        System.out.println("Linked list: "
                           + linkedList);

        // Converting LinkedList to Object Array
        Object[] objArray = convertLinkedListToArray(linkedList);

        // Convert Object[] to String[]
        String[] array = Arrays.copyOf(objArray,
                                       objArray.length,
                                       String[].class);
        // Print the String Array
        System.out.println("Array: "
                           + Arrays.toString(array));
    }
}
```

**Output:**

```java
Linked list: [G, e, e, k, s]
Array: [G, e, e, k, s]

```