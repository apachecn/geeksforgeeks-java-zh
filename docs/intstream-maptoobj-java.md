# Java 中的 intstream map oobject()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/intstream-map oobj-Java/

**IntStream mapToObj()** 返回由应用给定函数的结果组成的对象值流。

**注意:** IntStream mapToObj()是一个 ***的中间操作。*** 这些操作总是偷懒。中间操作在流实例上被调用，在它们完成处理后，它们给出一个流实例作为输出。
**语法:**

```
<U> Stream<U> mapToObj(IntFunction<? extends U> mapper)

```

**参数:**

1.  **U :** 新流的元素类型。
2.  **[流](https://www.geeksforgeeks.org/stream-in-java/) :** 支持顺序和并行聚合操作的元素序列。
3.  **IntFunction :** 表示接受 int 值参数并产生结果的函数。
4.  **映射器:**应用于每个元素的无状态函数。

**返回值:**该函数返回一个由应用给定函数的结果组成的对象值流。

**例 1 :**

```
// Java code for IntStream mapToObj
// (IntFunction mapper)
import java.util.*;
import java.util.stream.Stream;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.range(3, 8);

        // Creating a Stream of Strings
        // Using IntStream mapToObj(IntFunction mapper)
        // to store binary representation of
        // elements in IntStream
        Stream<String> stream1 = stream.mapToObj(num
                                                 -> Integer.toBinaryString(num));

        // Displaying an object-valued Stream
        // consisting of the results of
        // applying the given function.
        stream1.forEach(System.out::println);
    }
}
```

输出:

```
11
100
101
110
111

```

**例 2 :**

```
// Java code for IntStream mapToObj
// (IntFunction mapper)
import java.util.*;

import java.math.BigInteger;
import java.util.stream.Stream;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.of(3, 5, 7, 9, 11);

        // Creating a Stream
        // Using IntStream mapToObj(IntFunction mapper)
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

```
13
15
17
19
21

```