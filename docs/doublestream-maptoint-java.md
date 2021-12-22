# Java 中的 doublestream maptoint()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/double stream-map point-Java/

**DoubleStream mapToInt()** 返回一个 IntStream，它由给定函数应用于该流元素的结果组成。

**注意:**双流 mapToInt()是一个 ***中间操作。*** 这些操作总是偷懒。中间操作在流实例上被调用，在它们完成处理后，它们给出一个流实例作为输出。
**语法:**

```java
IntStream mapToInt(DoubleToIntFunction mapper)

```

**参数:**

1.  **IntStream :** 一系列原始的 int 值元素。这是[流](https://www.geeksforgeeks.org/stream-in-java/)的内部原始特化。
2.  **映射器:**应用于每个元素的无状态函数。

**返回值:**该函数返回一个 IntStream，该 int stream 由给定函数应用于该流元素的结果组成。

**例 1 :**

```java
// Java code for IntStream mapToInt
// (DoubleToIntFunction mapper)
import java.util.*;
import java.util.stream.IntStream;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a DoubleStream
        DoubleStream stream = DoubleStream.of(2.3, 4.5, 6.4,
                                              8.7, 10.4);

        // Using IntStream mapToInt(DoubleToIntFunction mapper)
        // to return an IntStream consisting of the
        // results of applying the given function to
        // the elements of this stream.
        IntStream stream1 = stream.mapToInt(num -> (int)num);

        // Displaying the elements in stream1
        stream1.forEach(System.out::println);
    }
}
```

输出:

```java
2
4
6
8
10

```

**例 2 :**

```java
// Java code for IntStream mapToInt
// (DoubleToIntFunction mapper)
import java.util.*;
import java.util.stream.IntStream;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a DoubleStream
        DoubleStream stream = DoubleStream.of(2.3, 4.5, 6.4,
                                              8.7, 10.4);

        // Using IntStream mapToInt(DoubleToIntFunction mapper)
        // to return an IntStream consisting of the
        // results of applying the given function to
        // the elements of this stream.
        IntStream stream1 = stream.mapToInt(num -> (int)num - 10000);

        // Displaying the elements in stream1
        stream1.forEach(System.out::println);
    }
}
```

输出:

```java
-9998
-9996
-9994
-9992
-9990

```

**例 3 :**

```java
// Java code for IntStream mapToInt
// (DoubleToIntFunction mapper)
import java.util.*;
import java.util.stream.IntStream;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a DoubleStream
        DoubleStream stream = DoubleStream.of(1.3, 2.4, 3.4,
                                              4.5, 5.7);

        // Using IntStream mapToInt(DoubleToIntFunction mapper)
        // to return an IntStream consisting of the
        // results of applying the given function to
        // the elements of this stream.
        IntStream stream1 = stream.mapToInt(num -> (int)(num * num * num));

        // Displaying the elements in stream1
        stream1.forEach(System.out::println);
    }
}
```

输出:

```java
2
13
39
91
185

```