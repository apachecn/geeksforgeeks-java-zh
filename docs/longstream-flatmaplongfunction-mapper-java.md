# Java 中的 LongStream flat map(long function mapper)

> 原文:[https://www . geesforgeks . org/longstream-flatmaplongfunction-mapper-Java/](https://www.geeksforgeeks.org/longstream-flatmaplongfunction-mapper-java/)

**LongStream flat map(long function mapper)**返回一个流，该流由将所提供的**映射函数**应用于每个元素而产生的映射流的内容替换该流的每个元素的结果组成。这是一个 ***中间操作*** 。这些操作总是偷懒。中间操作在流实例上被调用，在它们完成处理后，它们给出一个流实例作为输出。

**注意:**每个映射的流在其内容被放入该流后被关闭。如果映射的流为空，则改为使用空流。

**语法:**

```
LongStream flatMap(LongFunction<? extends LongStream> mapper)

```

**参数:**

1.  **LongStream :** 原始长值元素的序列。
2.  **LongFunction :** 接受长值参数并产生结果的函数。
3.  **映射器:**应用于每个元素的无状态函数，该函数返回新的流。

**返回值:**LongStream flat map(long function mapper)使用映射函数通过映射的流返回一个流。

**例 1 :** 使用 LongStream flatMap()获取 LongStream 元素的立方体。

```
// Java code for LongStream flatMap
// (LongFunction mapper) to get a stream
// consisting of the results of replacing
// each element of this stream with the
// contents of a mapped stream
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream1 = LongStream.of(4L, 5L, 6L, 7L);

        // Using LongStream flatMap()
        LongStream stream2 = stream1.flatMap(num
                      -> LongStream.of(num * num * num));

        // Displaying the resulting LongStream
        stream2.forEach(System.out::println);
    }
}
```

输出:

```
64
125
216
343

```

**示例 2 :** 使用 LongStream flatMap()获取 LongStream 元素的二进制表示中的集合位数。

```
// Java code for LongStream flatMap
// (LongFunction mapper) to get a stream
// consisting of the results of replacing
// each element of this stream with the
// contents of a mapped stream
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream1 = LongStream.of(49L, 64L, 81L, 100L);

        // Using LongStream flatMap()
        LongStream stream2 = stream1.flatMap(num
                        -> LongStream.of(Long.bitCount(num)));

        // Displaying the resulting LongStream
        stream2.forEach(System.out::println);
    }
}
```

输出:

```
3
1
3
3

```