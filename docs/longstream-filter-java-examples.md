# Java 中的 LongStream 过滤器()，示例

> 原文:[https://www . geesforgeks . org/longstream-filter-Java-examples/](https://www.geeksforgeeks.org/longstream-filter-java-examples/)

**LongStream filter(long 谓词谓词)**返回一个由该流中与给定谓词匹配的元素组成的流。这是一个 ***的中级操作。*** 这些操作总是懒惰的，即执行诸如 filter()的中间操作实际上并不执行任何过滤，而是创建一个新的流，当遍历该流时，它包含与给定谓词匹配的初始流的元素。

**语法:**

```
LongStream filter(LongPredicate predicate)

Where, LongStream is a sequence of primitive long-valued elements.
LongPredicate represents a predicate (boolean-valued function) 
of one long-valued argument and the function returns the new stream.

```

**例 1:**LongStream 上的 filter()方法。

```
// Java code for LongStream filter
// (LongPredicate predicate) to get a stream
// consisting of the elements of this
// stream that match the given predicate.
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream = LongStream.of(3L, 5L, 6L, 8L, 9L);

        // Using LongStream filter(LongPredicate predicate)
        // to get a stream consisting of the
        // elements that gives remainder 2 when
        // divided by 3
        stream.filter(num -> num % 3 == 2)
            .forEach(System.out::println);
    }
}
```

输出:

```
5
8

```

**例 2:**LongStream 上的 filter()方法。

```
// Java code for LongStream filter
// (LongPredicate predicate) to get a stream
// consisting of the elements of this
// stream that match the given predicate.
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream = LongStream.of(-2L, -1L, 0L, 1L, 2L);

        // Using LongStream filter(LongPredicate predicate)
        // to get a stream consisting of the
        // elements that are greater than 0
        stream.filter(num -> num > 0)
            .forEach(System.out::println);
    }
}
```

输出:

```
1
2

```