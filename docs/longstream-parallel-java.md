# Java 中的 LongStream parallel()

> 原文:[https://www.geeksforgeeks.org/longstream-parallel-java/](https://www.geeksforgeeks.org/longstream-parallel-java/)

**LongStream parallel()** 是 java.util.stream.LongStream 中的一个方法，这个方法返回一个并行的 LongStream，也就是说，它可能会自己返回，要么是因为流已经存在，要么是因为底层流状态被修改为并行。

LongStream parallel()是一个**中间操作**。这些操作总是偷懒。中间操作在流实例上被调用，在它们完成处理后，它们给出一个流实例作为输出。

**语法:**

```java
LongStream parallel()

Where, LongStream is a sequence of 
primitive long-valued elements and the function 
returns a parallel LongStream.

```

下面给出了一些例子来更好地理解这个函数。
**例 1 :**

```java
// Java program to demonstrate working of
// LongStream parallel() on a given range
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a stream of longs
        LongStream stream = LongStream.range(5L, 12L);

        System.out.println("The corresponding "
                           + "parallel LongStream is :");
        stream.parallel().forEach(System.out::println);
    }
}
```

输出:

```java
The corresponding parallel LongStream is :
9
8
11
10
6
5
7

```

**例 2 :**

```java
// Printing sequential stream for the
// same input as above example 1.
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        LongStream stream = LongStream.range(5L, 12L);

        System.out.println("The corresponding "
                           + "sequential LongStream is :");
        stream.sequential().forEach(System.out::println);
    }
}
```

输出:

```java
The corresponding sequential LongStream is :
5
6
7
8
9
10
11

```

**例 3 :**

```java
// Java program to show sorted output
// of parallel stream.
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a stream of longs
        LongStream stream = LongStream.of(3L, 4L, 1L, 5L,
                                          2L, 3L, 9L);

        System.out.println("The sorted parallel"
                           + " LongStream is :");
        stream.parallel().sorted().forEach(System.out::println);
    }
}
```

输出:

```java
The sorted parallel LongStream is :
4
2
3
9
3
5
1

```