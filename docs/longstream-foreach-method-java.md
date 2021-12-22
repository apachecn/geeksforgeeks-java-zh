# Java 中的 LongStream forEach()方法

> 原文:[https://www . geesforgeks . org/longstream-foreach-method-Java/](https://www.geeksforgeeks.org/longstream-foreach-method-java/)

**LongStream forEach(long consumer action)**为流的每个元素执行一个操作。LongStream forEach(long consumer action)是一个 ***终端操作*** ，也就是说，它可能会遍历该流以产生结果或副作用。

**语法:**

```java
void forEach(LongConsumer action)

```

**参数:** LongConsumer 表示接受单个长值参数且不返回结果的操作。这是消费者长期以来的原始型专业化。

**注意:**这个操作的行为是明确的**不确定的**。此外，对于任何给定的元素，动作可以在库选择的任何时间和任何线程中执行。

**例 1 :**

```java
// Java code for LongStream forEach
// (LongConsumer action) in Java 8
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream = LongStream.of(7L, 8L, 9L, 10L);

        // Using LongStream.forEach
        stream.forEach(System.out::println);
    }
}
```

**Output:**

```java
7
8
9
10

```

**例 2 :**

```java
// Java code for LongStream forEach
// (LongConsumer action) in Java 8
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream = LongStream.range(4L, 9L);

        // Using LongStream.forEach() on sequential stream
        stream.forEach(System.out::println);
    }
}
```

**Output:**

```java
4
5
6
7
8

```

**注意:**对于并行流，LongStream forEach(long consumer action)不保证尊重流的相遇顺序，因为这样做会牺牲并行的好处。下面是例子。

**例 3 :**

```java
// Java code for LongStream forEach
// (LongConsumer action) in Java 8
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream = LongStream.range(4L, 9L);

        // Using LongStream.forEach() on parallel stream
        stream.parallel().forEach(System.out::println);
    }
}
```

**Output:**

```java
6
8
7
5
4

```