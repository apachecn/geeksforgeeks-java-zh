# Java 中的 DoubleStream count()，示例

> 原文:[https://www . geesforgeks . org/double stream-count-Java-examples/](https://www.geeksforgeeks.org/doublestream-count-java-examples/)

**DoubleStream count()** 返回流中元素的计数。DoubleStream count()存在于 java.util.stream.DoubleStream 中，这是一种**约简**的特殊情况，即它采用一系列输入元素，并将它们组合成一个汇总结果。
**语法:**

```java
long count()

```

**注:**这是一个 ***终端操作*** 即可能穿越溪流产生结果或副作用。执行终端操作后，流管道被认为已消耗，不能再使用。

**例 1 :** 计算双流中的元素。

```java
// Java code for DoubleStream count()
// to count the number of elements in
// given stream
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // creating a DoubleStream
        DoubleStream stream = DoubleStream.of(2.3, 3.4, 4.5,
                                         5.6, 6.7, 7.8, 8.9);

        // storing the count of elements
        // in a variable named total
        long total = stream.count();

        // displaying the total number of elements
        System.out.println(total);
    }
}
```

**Output:**

```java
7

```

**例 2 :** 计算双流中不同的元素。

```java
// Java code for DoubleStream count()
// to count the number of distinct
// elements in given stream
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // creating a DoubleStream
        DoubleStream stream = DoubleStream.of(2.2, 3.3, 4.4,
                                        4.4, 7.6, 7.6, 8.0);

        // storing the count of distinct elements
        // in a variable named total
        long total = stream.distinct().count();

        // displaying the total number of elements
        System.out.println(total);
    }
}
```

**Output:**

```java
5

```