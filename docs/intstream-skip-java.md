# Java 中的 IntStream skip()

> 原文:[https://www.geeksforgeeks.org/intstream-skip-java/](https://www.geeksforgeeks.org/intstream-skip-java/)

**IntStream skip(long n)** 在丢弃流的前 n 个元素后，返回由该流的剩余元素组成的流。如果此流包含的元素少于 n 个，则将返回一个空流。

**注意:** IntStream skip()是一个 ***有状态的中间操作*** ，也就是说，在处理新元素时，它可能会合并来自之前看到的元素的状态。

**语法:**

```
IntStream skip(long n)

```

**参数:** IntStream 是一个原始的 int 值元素序列。这是[流](https://www.geeksforgeeks.org/stream-in-java/)的内部原始特化。 **n** 是要跳过的主导元素数量。

**返回值:**函数丢弃前 n 个元素后返回新的流。

**异常:**如果 n 为负，函数抛出***IllegalArgumentException***。

**例 1 :**

```
// Java code for IntStream skip() function
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream of numbers [5, 6, .. 11]
        IntStream stream = IntStream.range(5, 12);

        // Using skip() to skip first 4 values in range
        // and displaying the rest of elements
        stream.skip(4).forEach(System.out::println);
    }
}
```

输出:

```
9
10
11

```

**例 2 :**

```
// Java code for IntStream skip() function
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream [5, 6, .. 11]
        IntStream stream = IntStream.range(5, 12);

        // Using parallel skip() to skip first 4 values in range
        // and displaying the rest of elements
        stream.parallel().skip(4).forEach(System.out::println);
    }
}
```

输出:

```
10
11
9

```