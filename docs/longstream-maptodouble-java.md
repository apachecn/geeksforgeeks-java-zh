# Java 中的 LongStream mapToDouble()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/long stream-maptopoble-Java/

**LongStream mapToDouble()** 返回一个 DoubleStream，由给定函数应用于该流元素的结果组成。

**注:** LongStream mapToDouble()是一个*的**中间操作。*** 这些操作总是偷懒。中间操作在流实例上被调用，在它们完成处理后，它们给出一个流实例作为输出。
**语法:**

```java
DoubleStream mapToDouble(LongToDoubleFunction mapper)

```

**参数:**

1.  **双流:**原始双值元素的序列。这就是[流](https://www.geeksforgeeks.org/stream-in-java/)的双原始特化。
2.  **映射器:**应用于每个元素的无状态函数。

**返回值:**该函数返回一个双流，该双流由给定函数应用于该流元素的结果组成。

**例 1 :**

```java
// Java code for DoubleStream mapToDouble
// (LongToDoubleFunction mapper)
import java.util.*;
import java.util.stream.LongStream;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream = LongStream.of(2L, 4L, 6L, 8L, 10L);

        // Using DoubleStream mapToLong(LongToDoubleFunction mapper)
        // to return a DoubleStream consisting of the
        // results of applying the given function to
        // the elements of this stream.
        DoubleStream stream1 = stream.mapToDouble(num -> (double)num);

        // Displaying the elements in stream1
        stream1.forEach(System.out::println);
    }
}
```

输出:

```java
2.0
4.0
6.0
8.0
10.0

```

**例 2 :**

```java
// Java code for DoubleStream mapToDouble
// (LongToDoubleFunction mapper)
import java.util.*;
import java.util.stream.LongStream;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream = LongStream.range(5L, 10L);

        // Using DoubleStream mapToLong(LongToDoubleFunction mapper)
        // to return a DoubleStream consisting of the
        // results of applying the given function to
        // the elements of this stream.
        DoubleStream stream1 = stream.mapToDouble(num -> (double)num / 5);

        // Displaying the elements in stream1
        stream1.forEach(System.out::println);
    }
}
```

输出:

```java
1.0
1.2
1.4
1.6
1.8

```

**例 3 :**

```java
// Java code for DoubleStream mapToDouble
// (LongToDoubleFunction mapper)
import java.util.*;
import java.util.stream.LongStream;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream = LongStream.range(5L, 10L);

        // Using DoubleStream mapToLong(LongToDoubleFunction mapper)
        // to return a DoubleStream consisting of the
        // results of applying the given function to
        // the elements of this stream.
        DoubleStream stream1 = stream.mapToDouble(Math::cos);

        // Displaying the elements in stream1
        stream1.forEach(System.out::println);
    }
}
```

输出:

```java
0.28366218546322625
0.9601702866503661
0.7539022543433046
-0.14550003380861354
-0.9111302618846769

```