# Java 中的 intstream maptolong()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/intstream-map olong-Java/

**IntStream mapToLong()** 返回一个 LongStream，该 LongStream 由给定函数应用于该流元素的结果组成。

**注意:** IntStream mapToLong()是一个 ***的中间操作。*** 这些操作总是偷懒。中间操作在流实例上被调用，在它们完成处理后，它们给出一个流实例作为输出。
**语法:**

```
LongStream mapToLong(IntToLongFunction mapper)

```

**参数:**

1.  **LongStream :** 原始长值元素的序列。这是[溪流](https://www.geeksforgeeks.org/stream-in-java/)漫长的原始特化。
2.  **映射器:**应用于每个元素的无状态函数。

**返回值:**函数返回一个 LongStream，该 LongStream 由给定函数应用于该流元素的结果组成。

**例 1 :**

```
// Java code for LongStream mapToLong
// (IntToLongFunction mapper)
import java.util.*;
import java.util.stream.IntStream;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.of(2, 4, 6, 8, 10);

        // Using LongStream mapToLong(IntToLongFunction mapper)
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

```
2
4
6
8
10

```

**例 2 :**

```
// Java code for LongStream mapToLong
// (IntToLongFunction mapper)
import java.util.*;
import java.util.stream.IntStream;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.of(2, 4, 6, 8, 10);

        // Using LongStream mapToLong(IntToLongFunction mapper)
        // to return a LongStream consisting of the
        // results of applying the given function to
        // the elements of this stream.
        LongStream stream1 = stream.mapToLong(num -> (long)num + Integer.MAX_VALUE);

        // Displaying the elements in stream1
        stream1.forEach(System.out::println);
    }
}
```

输出:

```
2147483649
2147483651
2147483653
2147483655
2147483657

```

**例 3 :**

```
// Java code for LongStream mapToLong
// (IntToLongFunction mapper)
import java.util.*;
import java.util.stream.IntStream;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.range(5, 10);

        // Using LongStream mapToLong(IntToLongFunction mapper)
        // to return a LongStream consisting of the
        // results of applying the given function to
        // the elements of this stream.
        LongStream stream1 = stream.mapToLong(num -> (long)num - 20);

        // Displaying the elements in stream1
        stream1.forEach(System.out::println);
    }
}
```

输出:

```
-15
-14
-13
-12
-11

```