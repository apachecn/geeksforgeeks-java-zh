# 如何在 Java 中对 TreeSet 进行降序排序？

> 原文:[https://www . geesforgeks . org/how-sort-treeset-in-Java-降序排列/](https://www.geeksforgeeks.org/how-to-sort-treeset-in-descending-order-in-java/)

给定一个 Java 中的 [TreeSet](https://www.geeksforgeeks.org/treeset-in-java-with-examples/) ，任务是对 TreeSet 的元素进行降序排序。
**例:**

```
Input : Set: [2, 3, 5, 7, 10, 20]
Output : Set: [20, 10, 7, 5, 3, 2]

Input : Set: [computer, for, geeks, hello]
Output : Set: [hello, geeks, for, computer]

```

**方法:**
要使一个 TreeSet 元素按降序排列，只需使用 **descendingSet()** 方法，该方法用于以相反的顺序改变 TreeSet 的顺序
下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to print TreeSet in reverse Order
import java.util.TreeSet;

public class TreeSetDescending
{

    public static void main(String[] args)
    {
        // Declare a treeset
        TreeSet<Object> ints = new TreeSet<Object>();
        ints.add(2);
        ints.add(20);
        ints.add(10);
        ints.add(5);
        ints.add(7);
        ints.add(3);

        // Initialize treeset with
        // predefined set in reverse order
        // using descendingSet()
        TreeSet<Object> intsReverse =
            (TreeSet<Object>)ints.descendingSet();

        // Print the set
        System.out.println("Without descendingSet(): " +
                                                 ints);
        System.out.println("With descendingSet(): " +
                                           intsReverse);
    }
}
```

**Output**

```
Without descendingSet(): [2, 3, 5, 7, 10, 20]
With descendingSet(): [20, 10, 7, 5, 3, 2]

```