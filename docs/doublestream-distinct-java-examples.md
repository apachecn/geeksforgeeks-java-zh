# Java 中的双流 distinct()，示例

> 原文:[https://www . geesforgeks . org/double stream-distinct-Java-examples/](https://www.geeksforgeeks.org/doublestream-distinct-java-examples/)

**DoubleStream distinct()** 是 java.util.stream.DoubleStream 中的一个方法，这个方法返回一个由 distinct 元素组成的流。这是一个 ***有状态的中间操作*** ，也就是说，在处理新元素时，它可能会包含来自以前看到的元素的状态。在产生结果之前，他们可能需要处理整个输入。例如，在看到流的所有元素之前，无法对流进行排序。

**语法:**

```
DoubleStream distinct()

Where, DoubleStream is a sequence of 
primitive long-valued elements.

```

**例 1 :** 打印双流的不同元素。

```
// Java code for DoubleStream distinct()
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // creating a stream
        DoubleStream stream = DoubleStream.of(2.2, 3.3, 3.3,
                                        5.6, 6.7, 6.7, 8.0);

        // Displaying only distinct elements
        // using the distinct() method
        stream.distinct().forEach(System.out::println);
    }
}
```

输出:

```
2.2
3.3
5.6
6.7
8.0

```

**例 2 :** 双流中不同元素的计数值。

```
// Java code for DoubleStream distinct() method
// to count the number of distinct
// elements in given stream
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // creating a stream
        DoubleStream stream = DoubleStream.of(2.2, 3.3, 3.3,
                                         5.6, 6.7, 6.7, 8.0);

        // storing the count of distinct elements
        // in a variable named total
        long total = stream.distinct().count();

        // displaying the total number of elements
        System.out.println(total);
    }
}
```

输出:

```
5

```