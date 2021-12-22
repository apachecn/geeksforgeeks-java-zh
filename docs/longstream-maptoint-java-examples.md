# Java 中的 LongStream mapToInt()，示例

> 原文:[https://www . geesforgeks . org/longstream-maptoint-Java-examples/](https://www.geeksforgeeks.org/longstream-maptoint-java-examples/)

**LongStream mapToInt()** 返回一个 IntStream，它由给定函数应用于该流元素的结果组成。

**注意:** LongStream mapToInt()是一个*的**中间操作。*** 这些操作总是偷懒。中间操作在流实例上被调用，在它们完成处理后，它们给出一个流实例作为输出。
**语法:**

```
LongStream mapToInt(LongToIntFunction mapper)

```

**参数:**

1.  **LongStream :** 原始长值元素的序列。这是[溪流](https://www.geeksforgeeks.org/stream-in-java/)漫长的原始特化。
2.  **映射器:**应用于每个元素的无状态函数。

**返回值:**该函数返回一个 IntStream，该 int stream 由给定函数应用于该流元素的结果组成。

**例 1 :**

```
// Java code for LongStream mapToInt
// (LongToIntFunction mapper)
import java.util.*;
import java.util.stream.IntStream;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a LongStream
        LongStream stream = LongStream.of(2L, 4L, 6L, 8L, 10L);

        // Using LongStream mapToInt(LongToIntFunction mapper)
        // to return an IntStream consisting of the
        // results of applying the given function to 
        // the elements of this stream.
        IntStream stream1 = stream.mapToInt(num -> (int) num); 

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
// Java code for LongStream mapToInt
// (LongToIntFunction mapper)
import java.util.*;
import java.util.stream.IntStream;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a LongStream
        LongStream stream = LongStream.of(1L, 2L, 3L, 4L, 5L);

        // Using LongStream mapToInt(LongToIntFunction mapper)
        // to return an IntStream consisting of the
        // results of applying the given function to 
        // the elements of this stream.
        IntStream stream1 = stream.mapToInt(num ->
                                   (int) num + Integer.MAX_VALUE); 

        // Displaying the elements in stream1
        stream1.forEach(System.out::println);
    }
}
```

输出:

```
-2147483648
-2147483647
-2147483646
-2147483645
-2147483644

```

**例 3 :**

```
// Java code for LongStream mapToInt
// (LongToIntFunction mapper)
import java.util.*;
import java.util.stream.IntStream;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a LongStream
        LongStream stream = LongStream.range(2L, 7L);

        // Using LongStream mapToInt(LongToIntFunction mapper)
        // to return an IntStream consisting of the
        // results of applying the given function to 
        // the elements of this stream.
        IntStream stream1 = stream.mapToInt(num ->
                                    (int) num - 2); 

        // Displaying the elements in stream1
        stream1.forEach(System.out::println);
    }
}
```

输出:

```
0
1
2
3
4

```