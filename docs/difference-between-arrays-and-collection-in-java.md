# Java 中数组和集合的区别

> 原文:[https://www . geesforgeks . org/Java 中数组和集合的区别/](https://www.geeksforgeeks.org/difference-between-arrays-and-collection-in-java/)

[Java 中的一个数组](https://www.geeksforgeeks.org/arrays-in-java/)是一组相似类型的变量，用一个共同的名字来指代。Java 中的数组与 C/C++中的不同。以下是关于 Java 数组的一些要点。另一方面，表示为单个单元的任何一组单个对象被称为对象的[集合](https://www.geeksforgeeks.org/collections-in-java-2/)。在 Java 中，JDK 1.2 中定义了一个名为*“集合框架”*的独立框架，它包含了所有的集合类和接口。

处理 Collection 时最重要的是对 Collection 框架有超强的把握，如下图所示:

![](img/f8e668264eb7b2c4ec6dad3eaca56c3a.png)

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate Difference
// Between Arrays and Collection

// Importing required classes
import java.util.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Arrrays
        String[] gfg
            = new String[] { "G", "E", "E", "K", "S" };

        // Trying priting the above array
        System.out.print(gfg);

        // New Line
        System.out.println();

        // Collection
        // Let us arbitarly create an empty ArrayList
        // of string type
        ArrayList<String> al = new ArrayList<String>();

        // Adding elements to above List
        // using add() method
        al.add("g");
        al.add("e");
        al.add("e");
        al.add("k");
        al.add("s");

        // Printing all elements of Coolection (ArrayList)
        System.out.println(al);
    }
}
```

**Output**

```
[Ljava.lang.String;@3d075dc0
[g, e, e, k, s]
```

在了解了数组和集合之后，现在让我们将它们之间的差异列表如下:

<figure class="table">

| 数组 | 收藏品 |
| --- | --- |
| 数组的大小是固定的，也就是说，一旦我们创建了一个数组，我们就不能根据我们的需求增加或减少。 | 根据我们的要求，收藏品在性质上是可生长的。我们可以增加或减少尺寸。 |
| 对于内存，不建议使用阵列。 | 关于内存收集建议使用。 |
| 关于性能，建议使用阵列。 | 关于性能收集不建议使用。 |
| 数组只能保存同类数据类型元素。 | 集合可以包含同质和异质元素。 |
| 数组没有底层数据结构，因此现成的方法支持不可用。 | 每个集合类都是基于一些标准的数据结构实现的，因此对于每个需求，现成的方法支持都是一种性能。我们可以直接使用这些方法，我们不负责实现这些方法。 |
| 数组可以包含对象和基元。 | 集合只能保存对象类型，不能保存原始数据类型，如 int、long、short 等。 |

</figure>