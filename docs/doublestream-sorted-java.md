# Java 中的双流排序()

> 原文:[https://www.geeksforgeeks.org/doublestream-sorted-java/](https://www.geeksforgeeks.org/doublestream-sorted-java/)

**DoubleStream sorted()** 返回一个由这个流的元素按排序顺序组成的流。这是一个 ***有状态的中间操作*** ，也就是说，在处理新元素时，它可能会包含来自以前看到的元素的状态。有状态的中间操作可能需要在产生结果之前处理整个输入。例如，在看到流的所有元素之前，无法对流进行排序。

**语法:**

```
DoubleStream sorted()

Where, DoubleStream is a sequence of primitive double-valued 
elements. This is the double primitive specialization of Stream.

```

**返回值:** DoubleStream sorted()方法返回元素按排序顺序排列的新流。

**示例 1 :** 使用 DoubleStream sorted()对给定 DoubleStream 中的数字进行排序。

```
// Java code to sort DoubleStream
// using DoubleStream.sorted()
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream
        DoubleStream stream = DoubleStream.of(10.2, 9.3, 8.4,
                                              7.5, 6.6);

        // displaying the stream with sorted elements
        // using DoubleStream.sorted() function
        stream.sorted().forEach(System.out::println);
    }
}
```

**Output:**

```
6.6
7.5
8.4
9.3
10.2

```

**例 2 :** 使用 DoubleStream sorted()对 DoubleStream 生成器()生成的随机数进行排序。

```
// Java code to sort DoubleStream
// using DoubleStream.sorted()
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream by generating
        // random elements using DoubleStream.generate()
        DoubleStream stream = DoubleStream.generate(()
          -> (double)(Math.random() * 10000)).limit(5);

        // displaying the stream with sorted elements
        // using DoubleStream.sorted() function
        stream.sorted().forEach(System.out::println);
    }
}
```

**Output:**

```
1279.6146863795122
6927.016817313592
7037.390703089559
8374.314582282514
9112.609381925824

```