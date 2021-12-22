# Java 中的 IntStream 盒装()

> 原文:[https://www.geeksforgeeks.org/intstream-boxed-java/](https://www.geeksforgeeks.org/intstream-boxed-java/)

**int Stream box()**返回一个由该流的元素组成的流，每个元素都被装箱为一个整数。

**注意:** IntStream 盒装()是一个 ***的中间操作。*** 这些操作总是偷懒。中间操作在流实例上被调用，在它们完成处理后，它们给出一个流实例作为输出。
**语法:**

```java
Stream<Integer> boxed()

```

**参数:**

1.  **[流](https://www.geeksforgeeks.org/stream-in-java/) :** 支持顺序和并行聚合操作的元素序列。
2.  **Integer:**Integer 类包装对象中的图元类型 int 的值。整数类型的对象包含一个类型为整数的字段。

**返回值:**该函数返回一个装箱为整数的流。

**例 1 :**

```java
// Java code for IntStream boxed()
import java.util.*;
import java.util.stream.Stream;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.range(3, 8);

        // Creating a Stream of Integers
        // Using IntStream boxed() to return
        // a Stream consisting of the elements
        // of this stream, each boxed to an Integer.
        Stream<Integer> stream1 = stream.boxed();

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
// Java code for IntStream boxed()
import java.util.*;
import java.util.stream.Stream;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.range(3, 8);

        // Creating a Stream of Integers
        // Using IntStream boxed() to return
        // a Stream consisting of the elements
        // of this stream, each boxed to an Integer.
        Stream<Integer> stream1 = stream.boxed();

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