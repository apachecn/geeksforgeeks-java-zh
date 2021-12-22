# Java 中的 LongStream skip()

> 原文:[https://www.geeksforgeeks.org/longstream-skip-java/](https://www.geeksforgeeks.org/longstream-skip-java/)

**LongStream skip(long n)** 在丢弃流的前 n 个元素后，返回由该流的剩余元素组成的流。如果此流包含的元素少于 n 个，则将返回一个空流。

**注意:** LongStream skip()是一个 ***有状态的中间操作*** ，也就是说，在处理新元素时，它可能会合并来自之前看到的元素的状态。

**语法:**

```java
LongStream skip(long n)

```

**参数:** LongStream 是一个原始长值元素序列。这是[溪流](https://www.geeksforgeeks.org/stream-in-java/)漫长的原始特化。 **n** 是要跳过的主导元素数量。

**返回值:**函数丢弃前 n 个元素后返回新的流。

**异常:**如果 n 为负，函数抛出***IllegalArgumentException***。

**例 1 :**

```java
// Java code for LongStream skip() function
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream of numbers [5, 6, .. 11]
        LongStream stream = LongStream.range(5L, 12L);

        // Using skip() to skip first 4 values in range
        // and displaying the rest of elements
        stream.skip(4).forEach(System.out::println);
    }
}
```

**例 2 :**

```java
// Java code for LongStream skip() function
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream [5, 6, .. 11]
        LongStream stream = LongStream.range(5L, 12L);

        // Using parallel skip() to skip first
        // 4 values in range and displaying the
        // rest of elements
        stream.parallel().skip(4).forEach(System.out::println);
    }
}
```