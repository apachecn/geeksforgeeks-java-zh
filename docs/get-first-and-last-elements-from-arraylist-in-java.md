# 从 Java 的数组列表中获取第一个和最后一个元素

> 原文:[https://www . geesforgeks . org/get-first-and-last-elements-from-ArrayList-in-Java/](https://www.geeksforgeeks.org/get-first-and-last-elements-from-arraylist-in-java/)

给定一个数组列表，找到它的第一个和最后一个元素。

**示例:**

```java
Input : aList = {10, 30, 20, 14, 2}
Output : First = 10, Last = 2

Input : aList = {10, 30, 40, 50, 60}
Output : First = 10, Last = 60

```

最后一个元素位于 index，size–1，第一个元素存储在 index 0。如果我们知道如何[得到数组列表](https://www.geeksforgeeks.org/how-to-find-the-length-or-size-of-an-arraylist-in-java/)的大小，那么我们就可以很容易地得到这两个值。但是请记住，您需要对 ArrayList 使用 size()方法，而不是 length，length 用于获取数组的长度。

**查找数组列表中的第一个和最后一个:**

```java
// java program print first and last element of a List
import java.util.ArrayList;
import java.util.List;
public class FindFirstLast {
    public static void getFirstLat(List<Integer> list)
    {

        // Displaying ArrayList elements
        System.out.println("ArrayList contains: " + list);

        // Logic to get the last element from ArrayList
        if (list != null && !list.isEmpty()) {
            System.out.println("First element is: "
                               + list.get(0));
            System.out.println("Last element is: "
                               + list.get(list.size() - 1));
            return;
        }
    }

    public static void main(String[] args)
    {
        /* Creating ArrayList of Integer and adding
          elements to it */
        List<Integer> al = new ArrayList<Integer>();
        al.add(3);
        al.add(1);
        al.add(4);
        al.add(5);
        al.add(2);

        getFirstLat(al);
    }
}
```

**Output:**

```java
ArrayList contains: [3, 1, 4, 5, 2]
First element is: 3
Last element is: 2

```

**应用:**在升序的情况下，第一个元素是最低的，最后一个元素是最高的，反之，则第一个元素是最大的，如果列表是降序的，则最后一个元素是最小的。

```java
// java program print Maximum and Minimum Value of a
// sorted List, List may be increasing or decreasing order
import java.util.ArrayList;
import java.util.List;
public class FindFirstLast {
    // function find and print Maximum and Minimum value
    public static void getFirstLat(List<Integer> list)
    {

        // Displaying ArrayList elements
        System.out.println("ArrayList contains: " + list);

        // Logic to get the last element from ArrayList
        if (list != null && !list.isEmpty()) {
            if (list.get(0) < list.get(list.size() - 1)) {

                // if list in increasing order
                System.out.println("Minimum Value: "
                                   + list.get(0));
                System.out.println("Maximum Value: "
                           + list.get(list.size() - 1));
                return;
            }

            else {

                // if list in decreasing order
                System.out.println("Minimum Value: "
                            + list.get(list.size() - 1));
                System.out.println("Maximum Value: "
                                   + list.get(0));
                return;
            }
        }
    }

    public static void main(String[] args)
    {
        /* Creating ArrayList of Integer and adding
            elements to it */
        List<Integer> al = new ArrayList<Integer>();
        al.add(5);
        al.add(4);
        al.add(3);
        al.add(2);
        al.add(1);

        getFirstLat(al);
    }
}
```

**Output:**

```java
ArrayList contains: [5, 4, 3, 2, 1]
Minimum Value: 1
Maximum Value: 5

```