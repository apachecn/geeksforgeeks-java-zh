# Java 中的 LongStream 迭代器()

> 原文:[https://www.geeksforgeeks.org/longstream-iterator-java/](https://www.geeksforgeeks.org/longstream-iterator-java/)

**LongStream 迭代器()**返回该流元素的迭代器。这是一个 ***终端操作*** ，也就是说，它可能穿越河流产生结果或副作用。

**语法:**

```java
PrimitiveIterator.OfLong iterator()

Where, PrimitiveIterator.OfLong is an Iterator 
specialized for long values.

```

**返回值:** LongStream 迭代器()返回该流的元素迭代器。

**例 1 :**

```java
// Java code for LongStream iterator()
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream = LongStream.of(2L, 4L, 6L, 8L);

        // Using LongStream iterator() to return
        // an iterator for elements of the stream
        PrimitiveIterator.OfLong answer = stream.iterator();

        // Displaying the stream elements
        while (answer.hasNext()) {
            System.out.println(answer.nextLong());
        }
    }
}
```

**Output:**

```java
2
4
6
8

```

**例 2 :**

```java
// Java code for LongStream iterator()
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream which includes
        // lower bound element but excludes
        // upper bound element
        LongStream stream = LongStream.range(2L, 8L);

        // Using LongStream iterator() to return
        // an iterator for elements of the stream
        PrimitiveIterator.OfLong answer = stream.iterator();

        // Displaying the stream elements
        while (answer.hasNext()) {
            System.out.println(answer.nextLong());
        }
    }
}
```

**Output:**

```java
2
3
4
5
6
7

```