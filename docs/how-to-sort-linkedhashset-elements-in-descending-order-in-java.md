# 如何在 Java 中对 LinkedHashSet 元素进行降序排序？

> 原文:[https://www . geesforgeks . org/how-sort-link edhashset-elements-in-降序-java/](https://www.geeksforgeeks.org/how-to-sort-linkedhashset-elements-in-descending-order-in-java/)

链接哈希集是[哈希集](https://www.geeksforgeeks.org/hashset-in-java/)的有序版本，它维护所有元素的双向链表。当需要维护迭代顺序时，使用这个类。当遍历 HashSet 时，顺序是不可预测的，而 LinkedHashSet 迭代是按照元素插入的顺序遍历元素。当使用迭代器循环遍历 LinkedHashSet 时，元素将返回到它们被插入的顺序。

HashSet 中的元素保持顺序，而 TreeSet 中的对象保持排序顺序，排序顺序由 Java 中的[可比](https://www.geeksforgeeks.org/comparable-vs-comparator-in-java/)或[比较器](https://www.geeksforgeeks.org/comparator-interface-java/)方法定义。默认情况下，TreeSet 元素按升序排序。所以现在出现的问题是给定的 HashSet 按降序排列。因此，在 TreeSet 的帮助下，有必要以降序存储元素。

插图:

```
Input : LinkedHashSet = [4, 3, 6, 5, 8]
Output: LinkedHashSet = [8, 6, 5, 4, 3]

Input: LinkedHashSet = [22, 44, 33, 66, 55]
Output: LinkedHashSet = [66, 55, 44, 33, 22]
```

**算法**:

1.  创建 [HashSet](https://www.geeksforgeeks.org/hashset-in-java/) 接受用户输入并存储所有元素。
2.  现在，创建[树集](https://www.geeksforgeeks.org/treeset-in-java-with-examples/)，通过以相反的顺序添加上面的所有元素，以递减的顺序存储元素。

```
Pseude Code: TreeSet<Integer> ts = new TreeSet<>(Collections.reverseOrder());
             ts.addAll(lh);
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to sort LinkedHashSet elements
// in descending order

// Importing java generic libraries
import java.util.*;
import java.io.*;

// Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating and Initializing LinkedHashSet
        Set<Integer> linkhasset
            = new LinkedHashSet<Integer>();

        // Adding elements to above LinkedHashSet
        // Custom inputs
        linkhasset.add(26);
        linkhasset.add(23);
        linkhasset.add(24);
        linkhasset.add(21);
        linkhasset.add(25);
        linkhasset.add(22);

        // TreeSet storing elements in descending order by
        // adding all elements of HashSet in reverse order
        TreeSet<Integer> ts
            = new TreeSet<>(Collections.reverseOrder());

        // Add all elements from LinkedHashSet to TreeSet
        ts.addAll(linkhasset);

        // Print all elements of TreeSet
        System.out.println("Element in descending order : "
                           + ts);
    }
}
```

**Output**

```
Element in descending order : [26, 25, 24, 23, 22, 21]
```