# Java 中的 IntStream asLongStream()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/intstream-asongstream-Java/

**IntStream asLongStream()** 返回一个由该流的元素组成的 **LongStream** ，转换为 long。这是一个 ***的中级操作。*** 在流实例上调用中间操作，在它们完成处理后，它们给出一个流实例作为输出。

**语法:**

```java
LongStream asLongStream()

Where, LongStream is a sequence of 
primitive long-valued element.

```

**返回值:** IntStream asLongStream()返回一个由这个流的元素组成的 LongStream，转换为 long。

**例 1 :**

```java
// Java code for LongStream asLongStream()
// to return a LongStream consisting of
// the elements of this stream
import java.util.*;
import java.util.stream.IntStream;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.of(3, 5, 9, 12, 14);

        // Using LongStream asLongStream()
        LongStream stream1 = stream.asLongStream();

        // Displaying LongStream consisting of
        // the elements of this stream
        stream1.forEach(System.out::println);
    }
}
```

输出:

```java
3
5
9
12
14

```

**例 2 :**

```java
// Java code for LongStream asLongStream()
// to return a LongStream consisting of
// the elements of this stream
import java.util.*;
import java.util.stream.IntStream;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream and using asLongStream()
        LongStream stream = IntStream.range(3, 8).asLongStream();

        // Displaying LongStream consisting of
        // the elements of this stream
        stream.forEach(System.out::println);
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