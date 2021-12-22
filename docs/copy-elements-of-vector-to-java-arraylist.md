# 将向量的元素复制到 Java 数组列表中

> 原文:[https://www . geesforgeks . org/copy-elements-of-vector-to-Java-ArrayList/](https://www.geeksforgeeks.org/copy-elements-of-vector-to-java-arraylist/)

由于 [Vector](https://www.geeksforgeeks.org/java-util-vector-class-java/) 类和 [ArrayList](https://www.geeksforgeeks.org/arraylist-in-java/) 类都是 Java Collections 的一部分，即 [Collection 框架](https://www.geeksforgeeks.org/collections-in-java-2/)，因此这两个类都可以使用 Collection 框架可用的方法。Copy()方法是 Collection Interface 的方法之一，用于将一个列表复制到另一个列表，这里的列表可以是任何集合，如 ArrayList、LinkedList 和 Vector。

需要记住的一点是，如果目标列表的长度大于要复制的源列表的长度，那么另一个元素将保持不受影响，即如果目标列表的长度是 4，而源列表的长度是 3，那么目标列表的 3 个元素将被源列表的元素替换，但是第 4 个元素，即索引 3 处的元素，在目标列表中将保持不受影响。

**将** **向量的元素复制到数组列表**的方法

1.  传入构造函数
2.  使用 add()方法逐个添加

**方法 1:通过构造器**

*   在这种方法中，我们只需将一个向量传递给另一个列表的构造函数。
*   通过使用这种方法，如果我们改变第一个向量值，那么它不会改变列表的值。
*   这是将向量的元素复制到 Java 数组列表中最简单的方法。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program for copying Vector to List
// by passing in the constructor

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // creation of Vector of Integers
        Vector<Integer> gfg = new Vector<>();

        // adding elements to first Vector
        gfg.add(11);
        gfg.add(22);
        gfg.add(24);
        gfg.add(39);

        // passing in the constructor of List
        List<Integer> gfg2 = new ArrayList<>(gfg);

        // Iterating over second Vector
        System.out.println(
            "-----Iterating over the List----");

        for (Integer value : gfg2) {
            System.out.println(value);
        }
    }
}
```

**Output**

```
-----Iterating over the List----
11
22
24
39
```

**方法二:使用** [**<u>逐一添加()</u>**](https://www.geeksforgeeks.org/vector-add-method-in-java/) **方法**

*   在这种方法中，我们将迭代 Vector 的每个元素，并将该元素添加到列表中。
*   这里，如果你改变矢量元素，那么它不会改变列表的元素。
*   这不是最好的方法，但这是一个简单的迭代过程。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program for copying one Vector to the List
// by adding elements one by one using add() method

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // creation of Vector of Integers
        Vector<Integer> gfg = new Vector<>();

        // adding elements to first Vector
        gfg.add(50);
        gfg.add(24);
        gfg.add(95);
        gfg.add(31);

        List<Integer> gfg2 = new ArrayList<>();

        for (Integer value : gfg) {
            gfg2.add(value);
        }

        // Iterating over List
        System.out.println(
            "-----Iterating over the List----");

        for (Integer value : gfg2) {
            System.out.println(value);
        }
    }
}
```

**Output**

```
-----Iterating over the List----
50
24
95
31
```