# Java 中的双流映射(双流映射器)

> 原文:[https://www . geesforgeks . org/double stream-mapdoubleunaryooperator-mapper-Java/](https://www.geeksforgeeks.org/doublestream-mapdoubleunaryoperator-mapper-java/)

**双流映射(双流映射器)**返回一个流，该流由给定函数应用于该流元素的结果组成。这是一个*T3T5【中间操作】。这些操作总是偷懒。中间操作在流实例上被调用，在它们完成处理后，它们给出一个流实例作为输出。*

**语法:**

```
DoubleStream map(DoubleUnaryOperator mapper)

```

**参数:**

1.  **双流:**原始双值元素的序列。
2.  **双元运算符:**对单个双值操作数进行运算，产生双值结果。
3.  **映射器:**应用于每个元素的无状态函数，该函数返回新的流。

**返回值:**双流映射器(双流映射器)通过应用给定的函数返回一个流。

**例 1 :** 利用 DoubleStream 映射()得到 DoubleStream 元素平方的负值。

```
// Java code for DoubleStream map
// (DoubleUnaryOperator mapper) to get a
// stream by applying the given function.
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a DoubleStream
        DoubleStream stream1 = DoubleStream.of(4.4, 5.5, 6.3, 7.1);

        // Using DoubleStream map()
        DoubleStream stream2 = stream1.map(num -> (-num * num));

        // Displaying the resulting DoubleStream
        stream2.forEach(System.out::println);
    }
}
```

**Output:**

```
-19.360000000000003
-30.25
-39.69
-50.41

```

**例 2 :** 使用 DoubleStream map()获取 DoubleStream 的一半元素。

```
// Java code for DoubleStream map
// (DoubleUnaryOperator mapper) to get a
// stream by applying the given function.
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a DoubleStream
        DoubleStream stream1 = DoubleStream.of(2.2, 7.3, 8.2, 1.4);

        // Using DoubleStream map()
        DoubleStream stream2 = stream1.map(num -> (num / 2));

        // Displaying the resulting DoubleStream
        stream2.forEach(System.out::println);
    }
}
```

**Output:**

```
1.1
3.65
4.1
0.7

```