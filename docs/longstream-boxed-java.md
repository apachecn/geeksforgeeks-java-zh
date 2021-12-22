# Java 中的 LongStream 盒装()

> 原文:[https://www.geeksforgeeks.org/longstream-boxed-java/](https://www.geeksforgeeks.org/longstream-boxed-java/)

**LongStream box()**返回一个由该流的元素组成的流，每个元素被装箱为一个 Long。
**注:** LongStream 盒装()是一个 ***的中级操作。*** 这些操作总是偷懒。中间操作在流实例上被调用，在它们完成处理后，它们给出一个流实例作为输出。
**语法:**

```java
Stream<Long> boxed()

```

**参数:**

1.  **[流](https://www.geeksforgeeks.org/stream-in-java/) :** 支持顺序和并行聚合操作的元素序列。
2.  **Long:**Long 类在对象中包装一个长的基元类型的值。long 类型的对象包含类型为 Long 的单个字段。

**返回值:**该函数返回一个装箱为 Long 的流。

**例 1 :**

```java
// Java code for LongStream boxed()
import java.util.*;
import java.util.stream.Stream;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream = LongStream.range(3L, 8L);

        // Creating a Stream of Longs
        // Using LongStream boxed() to return
        // a Stream consisting of the elements
        // of this stream, each boxed to a Long.
        Stream<Long> stream1 = stream.boxed();

        // Displaying the elements
        stream1.forEach(System.out::println);
    }
}
```

输出:

```java
3
4
5
6
7

```

**例 2 :**

```java
// Java code for LongStream boxed()
import java.util.*;
import java.util.stream.Stream;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream = LongStream.range(3L, 8L);

        // Creating a Stream of Longs
        // Using LongStream boxed() to return
        // a Stream consisting of the elements
        // of this stream, each boxed to a Long.
        Stream<Long> stream1 = stream.boxed();

        Stream<Object> stream2 = Stream.concat(stream1,
                                    Stream.of("Geeks", "for", "Geeks"));

        // Displaying the elements
        stream2.forEach(System.out::println);
    }
}
```

输出:

```java
3
4
5
6
7
Geeks
for
Geeks

```