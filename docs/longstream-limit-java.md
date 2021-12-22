# Java 中的 LongStream limit()

> 原文:[https://www.geeksforgeeks.org/longstream-limit-java/](https://www.geeksforgeeks.org/longstream-limit-java/)

**LongStream limit(long maxSize)**返回由该流的元素组成的流，长度被截断为不超过 maxSize。

**注意:** LongStream limit()是一个 ***短路有状态中间操作*** ，即当用无限输入处理时，可能会产生一个有限的流作为结果，而不处理整个输入。

**语法:**

```java
LongStream limit(long maxSize)

```

**参数:**

1.  **LongStream :** 原始长值元素的序列。这是[溪流](https://www.geeksforgeeks.org/stream-in-java/)漫长的原始特化。
2.  **maxSize :** 流应该限制的元素数量。

**返回值:**函数返回一个由该流的元素组成的流，长度被截断为不超过 maxSize。

**异常:**如果 maxSize 为负，函数抛出***IllegalArgumentException***。

**例 1 :**

```java
// Java code for LongStream limit
// (long maxSize)
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream = LongStream.of(2L, 4L, 6L, 8L, 10L);

        // Using LongStream limit(long maxSize) to
        // get a stream consisting of the elements of
        // this stream, truncated to be no longer
        // than maxSize in length.
        stream.limit(3).forEach(System.out::println);
    }
}
```

输出:

```java
2
4
6

```

**例 2 :**

```java
// Java code for LongStream limit
// (long maxSize)
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream of numbers [5, 6, .. 11]
        LongStream stream = LongStream.range(5, 12);

        // Using LongStream limit(long maxSize) to
        // get a stream consisting of the elements of
        // this stream, truncated to be no longer
        // than maxSize in length.
        stream.limit(4).forEach(System.out::println);
    }
}
```

输出:

```java
5
6
7
8

```

**例 3 :**

```java
// Java code for LongStream limit
// (long maxSize)
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream = LongStream.iterate(4L, num -> num + 2);

        // Using LongStream limit(long maxSize) to
        // get a stream consisting of the elements of
        // this stream, truncated to be no longer
        // than maxSize in length.
        stream.limit(4).forEach(System.out::println);
    }
}
```

输出:

```java
4
6
8
10

```

【LongStream limit()和 [LongStream skip()](https://www.geeksforgeeks.org/longstream-skip-java/) 的区别:

1.  limit()方法返回第一个 maxSize 元素的缩减流，但 skip()方法在跳过第一个 maxSize 元素后返回剩余元素的流。
2.  limit()是一个短路的有状态中间操作，即当用无限输入处理时，它可能会产生一个有限的流，而不会处理整个输入，但是 skip()是一个有状态中间操作，即它可能需要在产生结果之前处理整个输入。