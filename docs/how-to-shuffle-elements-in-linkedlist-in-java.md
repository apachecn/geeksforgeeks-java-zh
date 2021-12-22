# 如何在 Java 中洗牌 LinkedList 中的元素？

> 原文:[https://www . geesforgeks . org/how-shuffle-elements-in-linked list-in-Java/](https://www.geeksforgeeks.org/how-to-shuffle-elements-in-linkedlist-in-java/)

[链接列表](https://www.geeksforgeeks.org/linked-list-in-java/)是 [java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)中的[收藏框架](https://www.geeksforgeeks.org/collections-in-java-2/)的一部分。这个类是[链表数据结构](https://www.geeksforgeeks.org/data-structures/linked-list/)的实现，这是一个线性数据结构，其中元素不存储在连续的位置，每个元素都是一个独立的对象，有数据部分和地址部分。这些元素使用指针和地址进行链接。每个元素都被称为一个节点。给定一个链接列表，任务是打乱链接列表。这些是解决问题的方法。

**方法 1(使用用户定义的方法)**

*   Create a **link list.**
*   Its elements are stored in the array by the **toarray ()** method.
*   Shuffle array elements.
*   Use the **list iterator** on the **linked list** , traverse the linked list by the **next ()** method, and store the shuffled data of the **array** into the list by the **set ()**

**示例**

## Java

```
import java.util.*;
public class GFG {

    public static void main(String args[])
    {

        // creating an instance of LinkedList
        LinkedList<Object> list = new LinkedList<>();

        // adding data to the LinkedList
        list.add(45);
        list.add("GFG");
        list.add(2.56f);
        list.add(965.321);
        list.add('A');
        list.add(true);

        System.out.println("The list before shuffle : "
                           + list.toString());
        System.out.println();

        // creating an Array and storing all data of the
        // list to the array
        Object[] array = list.toArray();

        // here we are shuffling more than once
        // shuffle 1
        arrayShuffle(array);
        listDataAdder(array, list);
        System.out.println("The list after shuffle 1 : "
                           + list.toString());
        System.out.println();

        // shuffle 2
        arrayShuffle(array);
        listDataAdder(array, list);
        System.out.println("The list after shuffle 2 : "
                           + list.toString());
        System.out.println();

        // shuffle 3
        arrayShuffle(array);
        listDataAdder(array, list);
        System.out.println("The list after shuffle 3 : "
                           + list.toString());
    }

    // Creating a data to add shuffled data of the array to
    // the list
    static void listDataAdder(Object[] arr,
                              LinkedList<Object> list)
    {
        // creating a ListIterator on the LinkedList
        ListIterator<Object> it = list.listIterator();

        // Traversing the LinkedList and setting all
        // shuffled data of the array to the list
        for (Object e : arr) {
            it.next();
            it.set(e);
        }
    }

    // creating a method to shuffle the array
    static void arrayShuffle(Object[] arr)
    {
        Random rand = new Random();
        for (int i = 0; i < arr.length - 1; i++) {

            // select index randomly
            int index = rand.nextInt(i + 1);

            // swapping between i th term and the index th
            // term
            Object g = arr[index];
            arr[index] = arr[i];
            arr[i] = g;
        }
    }
}
```

**输出**

```
The list before shuffle : [45, GFG, 2.56, 965.321, A, true]

The list after shuffle 1 : [965.321, 2.56, GFG, 45, A, true]

The list after shuffle 2 : [965.321, 45, A, 2.56, GFG, true]

The list after shuffle 3 : [965.321, 45, GFG, 2.56, A, true]
```