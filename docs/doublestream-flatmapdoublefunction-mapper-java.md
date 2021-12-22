# Java 中的双流平面图(双功能映射器)

> 原文:[https://www . geesforgeks . org/double stream-flat mapdouble function-mapper-Java/](https://www.geeksforgeeks.org/doublestream-flatmapdoublefunction-mapper-java/)

**双流平面图(双功能映射器)**返回一个流，该流由用映射流的内容替换该流的每个元素的结果组成，该映射流是通过将所提供的**映射函数**应用于每个元素而产生的。这是一个 ***中间操作*** 。这些操作总是偷懒。中间操作在流实例上被调用，在它们完成处理后，它们给出一个流实例作为输出。

**注意:**每个映射的流在其内容被放入该流后被关闭。如果映射的流为空，则改为使用空流。

**语法:**

```
DoubleStream flatMap(DoubleFunction<**?** extends DoubleStream> mapper)

```

**参数:**

1.  **双流:**原始双值元素的序列。
2.  **DoubleFunction :** 接受双值参数并产生结果的函数。
3.  **映射器:**应用于每个元素的无状态函数，该函数返回新的流。

**返回值:**double stream flat map(double function mapper)使用映射函数按映射流返回一个流。

**例 1 :** 使用 DoubleStream flatMap()获取 DoubleStream 元素的立方体。

```
// Java code for DoubleStream flatMap
// (DoubleFunction mapper) to get a stream
// consisting of the results of replacing
// each element of this stream with the
// contents of a mapped stream
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream
        DoubleStream stream1 = DoubleStream.of(4.2, 5.3, 6.6, 7.0);

        // Using DoubleStream flatMap()
        DoubleStream stream2 = stream1.flatMap(num
                   -> DoubleStream.of(num * num * num));

        // Displaying the resulting DoubleStream
        stream2.forEach(System.out::println);
    }
}
```

**Output:**

```
74.08800000000001
148.87699999999998
287.496
343.0

```

**示例 2 :** 使用 DoubleStream flatMap()将 DoubleStream 的每个元素乘以 0.7

```
// Java code for DoubleStream flatMap
// (DoubleFunction mapper) to get a stream
// consisting of the results of replacing
// each element of this stream with the
// contents of a mapped stream
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream
        DoubleStream stream1 = DoubleStream.of(5.2, 6.4, 8.1, 10.0);

        // Using DoubleStream flatMap()
        DoubleStream stream2 = stream1.flatMap(num
                     -> DoubleStream.of(num * 0.7));

        // Displaying the resulting IntStream
        stream2.forEach(System.out::println);
    }
}
```

**Output:**

```
3.6399999999999997
4.4799999999999995
5.669999999999999
7.0

```