# 如何在 Java 中对 HashSet 进行排序

> 原文:[https://www.geeksforgeeks.org/how-to-sort-hashset-in-java/](https://www.geeksforgeeks.org/how-to-sort-hashset-in-java/)

给定一个 Java 中的 HashSet，任务是对这个 HashSet 进行排序。

**示例:**

```
Input: HashSet: [Geeks, For, ForGeeks, GeeksforGeeks]
Output: [For, ForGeeks, Geeks, GeeksforGeeks]

Input: HashSet: [2, 5, 3, 1, 4]
Output: [1, 2, 3, 4, 5] 

```

[HashSet 类](https://www.geeksforgeeks.org/hashset-in-java/)实现了 Set 接口，由一个哈希表支持，该哈希表实际上是一个 HashMap 实例。不保证集合的迭代顺序，这意味着类不保证元素随时间的恒定顺序。

**表示 HashSet 不维持其元素的顺序。因此，哈希集的排序是不可能的。**

但是，HashSet 的元素可以通过转换为 List 或 TreeSet 来间接排序，但这将保持元素在目标类型中，而不是 HashSet 类型中。

下面是上述方法的实现:

**程序 1:** 通过将 HashSet 转换为 List。

```
// Java program to sort a HashSet

import java.util.*;

public class GFG {
    public static void main(String args[])
    {
        // Creating a HashSet
        HashSet<String> set = new HashSet<String>();

        // Adding elements into HashSet using add()
        set.add("geeks");
        set.add("practice");
        set.add("contribute");
        set.add("ide");

        System.out.println("Original HashSet: "
                           + set);

        // Sorting HashSet using List
        List<String> list = new ArrayList<String>(set);
        Collections.sort(list);

        // Print the sorted elements of the HashSet
        System.out.println("HashSet elements "
                           + "in sorted order "
                           + "using List: "
                           + list);
    }
}
```

**Output:**

```
Original HashSet: [practice, geeks, contribute, ide]
HashSet elements in sorted order using List: [contribute, geeks, ide, practice]

```

**程序 2:** 通过将 HashSet 转换为 TreeSet。

```
// Java program to sort a HashSet

import java.util.*;

public class GFG {
    public static void main(String args[])
    {

        // Creating a HashSet
        HashSet<String> set = new HashSet<String>();

        // Adding elements into HashSet using add()
        set.add("geeks");
        set.add("practice");
        set.add("contribute");
        set.add("ide");

        System.out.println("Original HashSet: "
                           + set);

        // Sorting HashSet using TreeSet
        TreeSet<String> treeSet = new TreeSet<String>(set);

        // Print the sorted elements of the HashSet
        System.out.println("HashSet elements "
                           + "in sorted order "
                           + "using TreeSet: "
                           + treeSet);
    }
}
```

**Output:**

```
Original HashSet: [practice, geeks, contribute, ide]
HashSet elements in sorted order using TreeSet: [contribute, geeks, ide, practice]

```