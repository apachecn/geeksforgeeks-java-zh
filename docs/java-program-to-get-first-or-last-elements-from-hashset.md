# 从 HashSet 获取第一个或最后一个元素的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-get-first-or-last-elements-from-hashset/](https://www.geeksforgeeks.org/java-program-to-get-first-or-last-elements-from-hashset/)

[*HashSet*](https://www.geeksforgeeks.org/hashset-in-java/) 类实现了 [Set 接口](https://www.geeksforgeeks.org/set-in-java/)，由一个哈希表支持，该哈希表实际上是一个 [HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java/) 实例。不保证集合的迭代顺序，这意味着类不保证元素随时间的恒定顺序。这个类允许空元素。该类还为基本操作(如添加、移除、包含和大小)提供了恒定的时间性能，假设哈希函数将元素适当地分散在桶中，我们将在本文中进一步看到这一点。

HashSet 不能保证元素的顺序随着时间的推移保持不变，这意味着当我们迭代一个 HashSet 时，不能保证我们得到的元素顺序与我们按顺序添加的相同。所以 HashSet 中没有第一个或最后一个元素。但是，我们可以根据 HashSet 存储元素的方式找到它的第一个或最后一个元素。通过简单的遍历 HashSet。

**接近:**

1.  插入、添加然后显示所需元素的简单方法。
2.  使用[流](https://www.geeksforgeeks.org/stream-in-java/)，借助 [*findFirst()*](https://www.geeksforgeeks.org/stream-findfirst-java-examples/) 和 *get()* 内置方法。

**示例 1:** 打印 HashMap 的第一个元素和最后一个元素。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Get First or
// Last Elements from Java HashSet

// Importing java generic libraries
import java.util.*;

public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating a HashSet
        HashSet<Integer> set = new HashSet<>();

        // Add data to Hashset
        set.add(10);
        set.add(20);
        set.add(20);
        set.add(10);
        set.add(50);
        set.add(40);

        // Initializing first element as 0 from outside
        // instead of garbage value involvement
        int firstEle = 0;

        // Iterate HashSet using for each loop
        for (int val : set) {
            firstEle = val;
            break;
        }

        // int lastEle = 0;

        // Print HashSet
        System.out.println("HashSet : " + set);

        // Print First element
        System.out.println("First element of HashSet : "
                           + firstEle);
    }
}
```

**Output**

```
HashSet : [50, 20, 40, 10]
First element of HashSet : 50
```

**方法二:**利用溪流寻找 HashSet 中的第一个元素，借助 Java 中的[*find first()*](https://www.geeksforgeeks.org/stream-findfirst-java-examples/)**和*得到()* 方法。**

****语法:****

```
set.stream().findFirst().get()
```

****返回类型:**返回 HashMap 的第一个元素**

****异常:**如果 HashSet 为空 ***get()*** 抛出错误(Java . util . nosucheelementexception)。**

****示例:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java code to find the first element
// in HashSet with the help of stream

// Importing generic java libraries
import java.util.*;

public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating a new HashSet
        HashSet<Integer> set = new HashSet<>();

        // Add data to Hashset
        set.add(10);
        set.add(20);
        set.add(20);
        set.add(10);
        set.add(50);
        set.add(40);

        // Find the first element in HashSet
        // using stream and findFirst method
        int firstEle = set.stream().findFirst().get();

        // Print HashSet
        System.out.println("HashSet : " + set);

        // Print First element of HashSet
        System.out.println("First element of HashSet : "
                           + firstEle);
    }
}
```

****Output**

```
HashSet : [50, 20, 40, 10]
First element of HashSet : 50
```**