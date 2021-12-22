# Java 中的 IntStream 过滤器()，示例

> 原文:[https://www . geesforgeks . org/int stream-filter-Java-examples/](https://www.geeksforgeeks.org/intstream-filter-java-examples/)

**IntStream 筛选器(IntPredicate 谓词)**返回一个由该流中与给定谓词匹配的元素组成的流。这是一个 ***的中级操作。*** 这些操作总是懒惰的，即执行诸如 filter()的中间操作实际上并不执行任何过滤，而是创建一个新的流，当遍历该流时，它包含与给定谓词匹配的初始流的元素。

**语法:**

```
IntStream filter(IntPredicate predicate)

Where, IntStream is a sequence of primitive int-valued elements.
IntPredicate represents a predicate (boolean-valued function) 
of one int-valued argument and the function returns the new stream.

```

**示例 1 :** 在 IntStream 上使用 filter()方法。

```
// Java code for IntStream filter
// (IntPredicate predicate) to get a stream
// consisting of the elements of this
// stream that match the given predicate.
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.of(3, 5, 6, 8, 9);

        // Using IntStream filter(IntPredicate predicate)
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

**示例 2 :** 在 IntStream 上使用 filter()方法。

```
// Java code for IntStream filter
// (IntPredicate predicate) to get a stream
// consisting of the elements of this
// stream that match the given predicate.
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.of(-2, -1, 0, 1, 2);

        // Using IntStream filter(IntPredicate predicate)
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