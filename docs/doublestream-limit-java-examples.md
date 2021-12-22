# Java 中的双流限制()，示例

> 原文:[https://www . geesforgeks . org/double stream-limit-Java-examples/](https://www.geeksforgeeks.org/doublestream-limit-java-examples/)

**double stream limit(long maxSize)**返回由该流的元素组成的流，长度被截断为不超过 maxSize。

**注意:** DoubleStream limit()是一个 ***短路有状态中间操作*** ，即当用无限输入处理时，可能会产生一个有限的流作为结果，而不处理整个输入。

**语法:**

```java
DoubleStream limit(long maxSize)

```

**参数:**

1.  **双流:**原始双值元素的序列。这就是[流](https://www.geeksforgeeks.org/stream-in-java/)的双原始特化。
2.  **maxSize :** 流应该限制的元素数量。

**返回值:**函数返回一个由该流的元素组成的流，长度被截断为不超过 maxSize。

**异常:**如果 maxSize 为负，函数抛出***IllegalArgumentException***。

**例 1 :**

```java
// Java code for DoubleStream limit
// (long maxSize)
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream
        DoubleStream stream = DoubleStream.of(2.3, 4.4, 6.7, 8.9, 10.5);

        // Using DoubleStream limit(long maxSize) to
        // get a stream consisting of the elements of
        // this stream, truncated to be no longer
        // than maxSize in length.
        stream.limit(3).forEach(System.out::println);
    }
}
```

输出:

```java
2.3
4.4
6.7

```

**例 2 :**

```java
// Java code for DoubleStream limit
// (long maxSize)
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream
        DoubleStream stream = DoubleStream.iterate(4.5, num -> num + 3);

        // Using DoubleStream limit(long maxSize) to
        // get a stream consisting of the elements of
        // this stream, truncated to be no longer
        // than maxSize in length.
        stream.limit(4).forEach(System.out::println);
    }
}
```

输出:

```java
4.5
7.5
10.5
13.5

```

**双流限制()和[双流跳过()](https://www.geeksforgeeks.org/doublestream-skip-java/)之间的差异:**

1.  limit()方法返回第一个 maxSize 元素的缩减流，但 skip()方法在跳过第一个 maxSize 元素后返回剩余元素的流。
2.  limit()是一个**短路有状态中间操作**，即当用无限输入处理时，它可能会产生一个有限的流作为结果而不处理整个输入，但是 skip()是一个**有状态中间操作**，即它可能需要在产生结果之前处理整个输入。