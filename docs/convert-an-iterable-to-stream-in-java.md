# 用 Java 将可迭代转换为流

> 原文:[https://www . geesforgeks . org/convert-an-iterable-to-stream-in-Java/](https://www.geeksforgeeks.org/convert-an-iterable-to-stream-in-java/)

给定一个 Iterable，任务是将其转换为 Java 中的 Stream。

**示例:**

```java
Input: Iterable = [1, 2, 3, 4, 5]
Output: {1, 2, 3, 4, 5}

Input: Iterable = ['G', 'e', 'e', 'k', 's']
Output: {'G', 'e', 'e', 'k', 's'}

```

**进场:**

1.  获取 Iterable。
2.  使用 Iterable.spliterator()方法将 Iterable 转换为 Spliterator。
3.  使用 StreamSupport.stream()方法将形成的拆分器转换为顺序流。
4.  返回流。

下面是上述方法的实现:

```java
// Java program to get a Stream
// from a given Iterable

import java.util.*;
import java.util.stream.*;

class GFG {

    // Function to get the Stream
    public static <T> Stream<T>
    getStreamFromIterable(Iterable<T> iterable)
    {

        // Convert the Iterable to Spliterator
        Spliterator<T>
            spliterator = iterable.spliterator();

        // Get a Sequential Stream from spliterator
        return StreamSupport.stream(spliterator, false);
    }

    // Driver code
    public static void main(String[] args)
    {

        // Get the Iterator
        Iterable<Integer>
            iterable = Arrays.asList(1, 2, 3, 4, 5);

        // Get the Stream from the Iterable
        Stream<Integer>
            stream = getStreamFromIterable(iterable);

        // Print the elements of stream
        stream.forEach(s -> System.out.println(s));
    }
}
```

**Output:**

```java
1
2
3
4
5

```