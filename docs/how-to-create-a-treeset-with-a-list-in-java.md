# 如何用 Java 创建带列表的树集？

> 原文:[https://www . geesforgeks . org/如何用 java 列表创建树集/](https://www.geeksforgeeks.org/how-to-create-a-treeset-with-a-list-in-java/)

[TreeSet](https://www.geeksforgeeks.org/treeset-in-java-with-examples/) 是 Java 中 [SortedSet 接口](https://www.geeksforgeeks.org/sortedset-java-examples/)的一个实现，使用[树](https://www.geeksforgeeks.org/binary-tree-data-structure/)进行存储。通过将列表传递给 Java 中的 TreeSet 构造函数，可以从[列表](https://www.geeksforgeeks.org/list-interface-java-examples/)创建 TreeSet，或者我们可以遍历完整的列表，并将列表的每个元素添加到 TreeSet 中。

**例:**

```
Input : List = [a, b, c]
Output: TreeSet = [a, b, c]

Input : List = [1, 2, 3]
Output: TreeSet = [1, 2, 3]
```

**方法 1:**

1.  Create a list object.
2.  Enter multiple inputs in the list.
3.  Create a treeset object.
4.  Initialize an object with a constructor and pass a List object in it.
5.  Print tree set.

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Create a TreeSet with a List
import java.util.ArrayList;
import java.util.List;
import java.util.TreeSet;

public class ExampleTreeSet {
    public static void main(String a[])
    {
        // Create new List
        List<String> fruitlist = new ArrayList<String>();
        fruitlist.add("Mango");
        fruitlist.add("Apple");
        fruitlist.add("Grape");
        fruitlist.add("Papaya");

        // Printing ArrayList
        System.out.println("Fruit List : " + fruitlist);

        // Create a TreeSet with the list
        TreeSet<String> tree_set
            = new TreeSet<String>(fruitlist);

        // Print TreeSet
        System.out.println("TreeSet from List : "
                           + tree_set);
    }
}
```

**Output**

```
Fruit List : [Mango, Apple, Grape, Papaya]
TreeSet from List : [Apple, Grape, Mango, Papaya]
```

**时间复杂度:** O(N)

**方法 2:**

1.  Create a list object.
2.  Enter multiple inputs in the list.
3.  Create a treeset object.
4.  Start the list traversal and add the element to the tree set.
5.  After traversing, print the tree set.

下面是上述方法的实现:

T3】JavaT5

```
// Java Program to Create a TreeSet with a List
import java.util.ArrayList;
import java.util.List;
import java.util.TreeSet;

public class ExampleTreeSet {
    public static void main(String a[])
    {
        // Create new List
        List<String> fruitlist = new ArrayList<String>();
        fruitlist.add("Mango");
        fruitlist.add("Apple");
        fruitlist.add("Grape");
        fruitlist.add("Papaya");

        // Printing ArrayList
        System.out.println("Fruit List : " + fruitlist);

        // Create a TreeSet
        TreeSet<String> tree_set = new TreeSet<String>();

        // Add each element in the TreeSet
        for (String i : fruitlist)
            tree_set.add(i);

        // Print TreeSet
        System.out.println("TreeSet from List : "
                           + tree_set);
    }
}
```

T6T8**输出**T1

**时间复杂度:** O(N)