# Java 中的双流迭代器()

> 原文:[https://www.geeksforgeeks.org/doublestream-iterator-java/](https://www.geeksforgeeks.org/doublestream-iterator-java/)

**双流迭代器()**返回该流元素的迭代器。这是一个 ***终端操作*** ，也就是说，它可能穿越河流产生结果或副作用。执行终端操作后，流管道被认为已消耗，不能再使用。如果需要再次遍历同一数据源，则必须返回数据源以获取新的流。

**语法:**

```java
PrimitiveIterator.OfDouble iterator()

Where, PrimitiveIterator.OfDouble is an Iterator 
specialized for double values.

```

**返回值:** DoubleStream 迭代器()返回该流的元素迭代器。

**例:**

```java
// Java code for DoubleStream iterator()
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a DoubleStream
        DoubleStream stream = DoubleStream.of(2.3, 4.4, 6.5, 8.2);

        // Using DoubleStream iterator() to return
        // an iterator for elements of the stream
        PrimitiveIterator.OfDouble answer = stream.iterator();

        // Displaying the stream elements
        while (answer.hasNext()) {
            System.out.println(answer.nextDouble());
        }
    }
}
```

**输出:**

```java
2.3
4.4
6.5
8.2

```