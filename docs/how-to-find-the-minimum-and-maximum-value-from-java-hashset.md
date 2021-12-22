# 如何从 Java HashSet 中找到最小值和最大值？

> 原文:[https://www . geesforgeks . org/如何从 java-hashset 中找到最小和最大值/](https://www.geeksforgeeks.org/how-to-find-the-minimum-and-maximum-value-from-java-hashset/)

[**HashSet**](https://www.geeksforgeeks.org/hashset-in-java/) 用于在 Java 中存储不同的值。HashSet 不能保证元素的顺序随着时间的推移保持不变，这意味着当我们迭代一个 HashSet 时，不能保证我们得到的元素顺序与我们按顺序添加的相同。HashSet 不提供任何获取最大值和最小值的内置方法。

有两种方法可以从 Java 的 HashSet 中找到最大值和最小值:

1.  使用集合类
2.  使用简单迭代

**方法一:使用** [**集合**](https://www.geeksforgeeks.org/collections-in-java-2/) **类**

使用 Java 中的 Collections 类，借助 Collections 类的 **max()** 和 **min()** 方法，可以找到最大值和最小值。

**代码:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to find the maximum and minimum in HashSet

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // New HashSet
        HashSet<Integer> set = new HashSet<>();

        // Add data to Hashset
        set.add(10);
        set.add(20);
        set.add(20);
        set.add(10);
        set.add(50);
        set.add(40);

        // Print Maximum value using max method of
        // Collections class
        System.out.println("Maximum value of HashSet : "
                           + Collections.max(set));

        // Print Maximum value using max method of
        // Collections class
        System.out.println("Minimum value of HashSet : "
                           + Collections.min(set));
    }
}
```

**Output**

```
Maximum value of HashSet : 50
Minimum value of HashSet : 10
```

**方法二:使用简单迭代**

我们可以通过简单地迭代 HashSet 来找到最大值和最小值，维护最小值和最大值变量，并在遍历每个元素并将其与最小值和最大值进行比较时相应地更新它。

**代码:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to find the maximum and minimum in HashSet

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // New HashSet
        HashSet<Integer> set = new HashSet<>();

        // Add data to Hashset
        set.add(10);
        set.add(20);
        set.add(20);
        set.add(10);
        set.add(50);
        set.add(40);

        int max = -1, min = -1;

        // Iterate HashSet to get Maximum value
        for (int val : set) {
            if (max == -1) {
                max = val;
            }
            else if (val > max) {
                max = val;
            }
        }

        // Iterate HashSet to get Minimum value
        for (int val : set) {
            if (min == -1) {
                min = val;
            }
            else if (val < min) {
                min = val;
            }
        }

        // Print Maximum value using max method of
        // Collections class
        System.out.println("Maximum value of HashSet : "
                           + max);

        // Print Maximum value using max method of
        // Collections class
        System.out.println("Minimum value of HashSet : "
                           + min);
    }
}
```

**Output**

```
Maximum value of HashSet : 50
Minimum value of HashSet : 10
```