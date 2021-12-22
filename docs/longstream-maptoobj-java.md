# Java 中的长流 map oobject()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/long stream-map oobj-Java/

**LongStream mapToObj()** 返回由应用给定函数的结果组成的对象值流。

**注意:** LongStream mapToObj()是一个*的**中间操作。*** 这些操作总是偷懒。中间操作在流实例上被调用，在它们完成处理后，它们给出一个流实例作为输出。
**语法:**

```java
<U> Stream<U> mapToObj(LongFunction<? extends U> mapper)

```

**参数:**

1.  **U :** 新流的元素类型。
2.  **[流](https://www.geeksforgeeks.org/stream-in-java/) :** 支持顺序和并行聚合操作的元素序列。
3.  **LongFunction :** 表示接受长值参数并产生结果的函数。
4.  **映射器:**应用于每个元素的无状态函数。

**返回值:**该函数返回一个由应用给定函数的结果组成的对象值流。

**例 1 :**

```java
// Java code for LongStream mapToObj
// (LongFunction mapper)
import java.util.*;
import java.util.stream.Stream;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream = LongStream.range(3L, 8L);

        // Creating a Stream of Strings
        // Using LongStream mapToObj(LongFunction mapper)
        // to store binary representation of
        // elements in LongStream
        Stream<String> stream1 = stream.mapToObj(num
                                                 -> Long.toBinaryString(num));

        // Displaying an object-valued Stream
        // consisting of the results of
        // applying the given function.
        stream1.forEach(System.out::println);
    }
}
```

输出:

```java
11
100
101
110
111

```

**例 2 :**

```java
// Java code for LongStream mapToObj
// (LongFunction mapper)
import java.util.*;

import java.math.BigInteger;
import java.util.stream.Stream;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream = LongStream.of(3L, 5L, 7L, 9L, 11L);

        // Creating a Stream
        // Using LongStream mapToObj(LongFunction mapper)
        Stream<BigInteger> stream1 = stream
                                         .mapToObj(BigInteger::valueOf);

        // Displaying an object-valued Stream
        // consisting of the results of
        // applying the given function.
        stream1.forEach(num -> System.out.println(num.add(BigInteger.TEN)));
    }
}
```

输出:

```java
13
15
17
19
21

```