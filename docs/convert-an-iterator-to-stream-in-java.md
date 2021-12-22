# 用 Java 将迭代器转换为流

> 原文:[https://www . geesforgeks . org/convert-a-iterator-to-stream-in-Java/](https://www.geeksforgeeks.org/convert-an-iterator-to-stream-in-java/)

给定一个迭代器，任务是将其转换为 Java 中的 Stream。

**示例:**

```java
Input: Iterator = {1, 2, 3, 4, 5}
Output: {1, 2, 3, 4, 5}

Input: Iterator = {'G', 'e', 'e', 'k', 's'}
Output: {'G', 'e', 'e', 'k', 's'}

```

**进场:**

1.  获取迭代器。
2.  使用 spliterators . spliteratorrunknownsize()方法将迭代器转换为 Spliterator。
3.  使用 StreamSupport.stream()方法将形成的拆分器转换为顺序流。
4.  返回流。

下面是上述方法的实现:

```java
// Java program to get a Stream
// from a given Iterator

import java.util.*;
import java.util.stream.*;

class GFG {

    // Function to get the Stream
    public static <T> Stream<T>
    getStreamFromIterator(Iterator<T> iterator)
    {

        // Convert the iterator to Spliterator
        Spliterator<T>
            spliterator = Spliterators
                              .spliteratorUnknownSize(iterator, 0);

        // Get a Sequential Stream from spliterator
        return StreamSupport.stream(spliterator, false);
    }

    // Driver code
    public static void main(String[] args)
    {

        // Get the Iterator
        Iterator<Integer>
            iterator = Arrays.asList(1, 2, 3, 4, 5)
                           .iterator();

        // Get the Stream from the Iterator
        Stream<Integer>
            stream = getStreamFromIterator(iterator);

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