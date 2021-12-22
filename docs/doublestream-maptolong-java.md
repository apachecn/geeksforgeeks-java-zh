# Java 中的 DoubleStream mapToLong()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/double stream-map color-Java/

**DoubleStream mapToLong()** 返回一个 LongStream，该 LongStream 由给定函数应用于该流元素的结果组成。

**注:**双流 mapToLong()是一个 ***的中间操作。*** 这些操作总是偷懒。中间操作在流实例上被调用，在它们完成处理后，它们给出一个流实例作为输出。
**语法:**

```java
LongStream mapToLong(DoubleToLongFunction mapper)

```

**参数:**

1.  **双流:**原始双值元素的序列。这就是[流](https://www.geeksforgeeks.org/stream-in-java/)的双原始特化。
2.  **映射器:**应用于每个元素的无状态函数。

**返回值:**函数返回一个 LongStream，该 LongStream 由给定函数应用于该流元素的结果组成。

**例 1 :**

```java
// Java code for LongStream mapToLong
// (DoubleToLongFunction mapper)
import java.util.*;
import java.util.stream.LongStream;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a DoubleStream
        DoubleStream stream = DoubleStream.of(3.3, 6.5, 16.4,
                                              8.7, 10.4);

        // Using LongStream mapToLong(DoubleToLongFunction mapper)
        // to return a LongStream consisting of the
        // results of applying the given function to
        // the elements of this stream.
        LongStream stream1 = stream.mapToLong(num -> (long)num);

        // Displaying the elements in stream1
        stream1.forEach(System.out::println);
    }
}
```

输出:

```java
3
6
16
8
10

```

**例 2 :**

```java
// Java code for LongStream mapToLong
// (DoubleToLongFunction mapper)
import java.util.*;
import java.util.stream.LongStream;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a DoubleStream
        DoubleStream stream = DoubleStream.of(3.3, 6.5, 16.4,
                                              8.7, 10.4);

        // Using LongStream mapToLong(DoubleToLongFunction mapper)
        // to return a LongStream consisting of the
        // results of applying the given function to
        // the elements of this stream.
        LongStream stream1 = stream.mapToLong(num -> (long)num - 10);

        // Displaying the elements in stream1
        stream1.forEach(System.out::println);
    }
}
```

输出:

```java
-7
-4
6
-2
0

```

**例 3 :**

```java
// Java code for LongStream mapToLong
// (DoubleToLongFunction mapper)
import java.util.*;
import java.util.stream.LongStream;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a DoubleStream
        DoubleStream stream = DoubleStream.of(3.3, 6.5, 16.4,
                                              8.7, 10.4);

        // Using LongStream mapToLong(DoubleToLongFunction mapper)
        // to return a LongStream consisting of the
        // results of applying the given function to
        // the elements of this stream.
        LongStream stream1 = stream.mapToLong(num -> (long)(2 * num * num));

        // Displaying the elements in stream1
        stream1.forEach(System.out::println);
    }
}
```

输出:

```java
21
84
537
151
216

```