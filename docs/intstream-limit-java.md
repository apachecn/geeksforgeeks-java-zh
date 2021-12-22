# Java 中的 IntStream 限制()

> 原文:[https://www.geeksforgeeks.org/intstream-limit-java/](https://www.geeksforgeeks.org/intstream-limit-java/)

**int stream limit(long maxSize)**返回由该流的元素组成的流，长度被截断为不超过 maxSize。

**注意:** IntStream limit()是一个 ***短路有状态中间操作*** ，即当用无限输入处理时，可能会产生一个有限的流作为结果，而不处理整个输入。

**语法:**

```java
IntStream limit(long maxSize)

```

**参数:**

1.  **IntStream :** 一系列原始的 int 值元素。这是[流](https://www.geeksforgeeks.org/stream-in-java/)的内部原始特化。
2.  **maxSize :** 流应该限制的元素数量。

**返回值:**函数返回一个由该流的元素组成的流，长度被截断为不超过 maxSize。

**异常:**如果 maxSize 为负，函数抛出***IllegalArgumentException***。

**例 1 :**

```java
// Java code for IntStream limit
// (long maxSize)
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.of(2, 4, 6, 8, 10);

        // Using IntStream limit(long maxSize) to
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
// Java code for IntStream limit
// (long maxSize)
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream of numbers [5, 6, .. 11]
        IntStream stream = IntStream.range(5, 12);

        // Using IntStream limit(long maxSize) to
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
// Java code for IntStream limit
// (long maxSize)
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.iterate(4, num -> num + 2);

        // Using IntStream limit(long maxSize) to
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

【IntStream limit()和 [IntStream skip()](https://www.geeksforgeeks.org/intstream-skip-java/) 的区别:

1.  limit()方法返回第一个 maxSize 元素的缩减流，但 skip()方法在跳过第一个 maxSize 元素后返回剩余元素的流。
2.  limit()是一个短路的有状态中间操作，即当用无限输入处理时，它可能会产生一个有限的流，而不会处理整个输入，但是 skip()是一个有状态中间操作，即它可能需要在产生结果之前处理整个输入。