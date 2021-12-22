# Java 中的 LongStream asDoubleStream()

> 原文:[https://www . geesforgeks . org/longstream-as double stream-Java/](https://www.geeksforgeeks.org/longstream-asdoublestream-java/)

**LongStream as double stream()**返回一个由该流的元素组成的 **DoubleStream** ，转换为 double。这是一个 ***的中级操作。*** 在流实例上调用中间操作，在它们完成处理后，它们给出一个流实例作为输出。

**语法:**

```java
DoubleStream asDoubleStream()

Where, DoubleStream is a sequence of 
primitive double-valued element.

```

**返回值:** LongStream asDoubleStream()返回由该流的元素组成的 DoubleStream，转换为 double。

**例 1 :**

```java
// Java code for DoubleStream asDoubleStream()
// to return a DoubleStream consisting of
// the elements of this stream
import java.util.*;
import java.util.stream.LongStream;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a LongStream
        LongStream stream = LongStream.of(3L, 5L, 9L, 12L, 14L);

        // Using DoubleStream asDoubleStream()
        DoubleStream stream1 = stream.asDoubleStream();

        // Displaying DoubleStream consisting of
        // the elements of this stream
        stream1.forEach(System.out::println);
    }
}
```

输出:

```java
3.0
5.0
9.0
12.0
14.0

```

**例 2 :**

```java
// Java code for DoubleStream asDoubleStream()
// to return a DoubleStream consisting of
// the elements of this stream
import java.util.*;
import java.util.stream.LongStream;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream and using asDoubleStream()
        DoubleStream stream = LongStream.range(3L, 8L)
                                  .asDoubleStream();

        // Displaying DoubleStream consisting of
        // the elements of this stream
        stream.forEach(System.out::println);
    }
}
```

输出:

```java
3.0
4.0
5.0
6.0
7.0

```

**例 3 :**

```java
// Java code for DoubleStream asDoubleStream()
// to return a DoubleStream consisting of
// the elements of this stream
import java.util.*;
import java.util.stream.LongStream;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a LongStream and using asDoubleStream()
        // to display the elements of LongStream and
        // DoubleStream together
        DoubleStream stream = LongStream.range(3L, 8L)
                                  .peek(System.out::println)
                                  .asDoubleStream();

        // Displaying DoubleStream consisting of
        // the elements of this stream
        stream.forEach(System.out::println);
    }
}
```

输出:

```java
3
3.0
4
4.0
5
5.0
6
6.0
7
7.0

```