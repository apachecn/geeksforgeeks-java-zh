# Java 中的 LongStream peek()，带示例

> 原文:[https://www . geesforgeks . org/longstream-peek-Java-examples/](https://www.geeksforgeeks.org/longstream-peek-java-examples/)

**LongStream peek()** 是 java.util.stream.LongStream 中的一个方法，该函数返回一个由这个流的元素组成的流，当从结果流中消费元素时，还会对每个元素执行提供的操作。

**语法:**

```java
LongStream peek(LongConsumer action)

Where, LongStream is a sequence of primitive
long-valued elements and the function returns 
a parallel LongStream and LongConsumer represents 
an operation that accepts a single long-valued argument.

```

**示例 1 :** 对给定范围的流执行求和。

```java
// Java code for LongStream peek()
// where the action performed is to get
// sum of all elements in given range
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a stream of longs
        LongStream stream = LongStream.range(2L, 10L);

        // performing action sum on elements of
        // given range and storing the result in sum
        long sum = stream.peek(System.out::println).sum();

        // Displaying the result of action performed
        System.out.println("sum is : " + sum);
    }
}
```

**输出:**

```java
2
3
4
5
6
7
8
9
sum is : 44

```