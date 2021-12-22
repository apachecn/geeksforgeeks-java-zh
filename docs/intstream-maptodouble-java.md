# Java 中的 intstream maptodouble()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/intstream-maptopoble-Java/

**IntStream mapToDouble()** 返回一个 DoubleStream，由给定函数应用于该流元素的结果组成。

**注意:** IntStream mapToDouble()是一个*的**中间操作。*** 这些操作总是偷懒。中间操作在流实例上被调用，在它们完成处理后，它们给出一个流实例作为输出。
**语法:**

```java
DoubleStream mapToDouble(IntToDoubleFunction mapper)

```

**参数:**

1.  **双流:**原始双值元素的序列。这就是[流](https://www.geeksforgeeks.org/stream-in-java/)的双原始特化。
2.  **映射器:**应用于每个元素的无状态函数。

**返回值:**该函数返回一个双流，该双流由给定函数应用于该流元素的结果组成。

**例 1 :**

```java
// Java code for DoubleStream mapToDouble
// (IntToDoubleFunction mapper)
import java.util.*;
import java.util.stream.IntStream;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.of(2, 4, 6, 8, 10);

        // Using DoubleStream mapToLong(IntToDoubleFunction mapper)
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
// (IntToDoubleFunction mapper)
import java.util.*;
import java.util.stream.IntStream;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.range(5, 10);

        // Using DoubleStream mapToLong(IntToDoubleFunction mapper)
        // to return a DoubleStream consisting of the
        // results of applying the given function to
        // the elements of this stream.
        DoubleStream stream1 = stream.mapToDouble(num -> (double)num / 3);

        // Displaying the elements in stream1
        stream1.forEach(System.out::println);
    }
}
```

输出:

```java
1.6666666666666667
2.0
2.3333333333333335
2.6666666666666665
3.0

```

**例 3 :**

```java
// Java code for DoubleStream mapToDouble
// (IntToDoubleFunction mapper)
import java.util.*;
import java.util.stream.IntStream;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.range(5, 10);

        // Using DoubleStream mapToLong(IntToDoubleFunction mapper)
        // to return a DoubleStream consisting of the
        // results of applying the given function to
        // the elements of this stream.
        DoubleStream stream1 = stream.mapToDouble(Math::sin);

        // Displaying the elements in stream1
        stream1.forEach(System.out::println);
    }
}
```

输出:

```java
-0.9589242746631385
-0.27941549819892586
0.6569865987187891
0.9893582466233818
0.4121184852417566

```