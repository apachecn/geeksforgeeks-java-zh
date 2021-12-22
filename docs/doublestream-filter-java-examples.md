# Java 中的 DoubleStream 过滤器()，示例

> 原文:[https://www . geesforgeks . org/double stream-filter-Java-examples/](https://www.geeksforgeeks.org/doublestream-filter-java-examples/)

**双流过滤器(双谓词谓词)**返回一个由该流中与给定谓词匹配的元素组成的流。这是一个 ***的中级操作。*** 这些操作总是懒惰的，即执行诸如 filter()的中间操作实际上并不执行任何过滤，而是创建一个新的流，当遍历该流时，它包含与给定谓词匹配的初始流的元素。

**语法:**

```java
DoubleStream filter(DoublePredicate predicate)

```

**参数:**

1.  **双流:**原始双值元素的序列。
2.  **双谓词:**一个双值参数的谓词(布尔值函数)。

**返回值:**函数返回新的流。

**示例 1 :** 在 DoubleStream 上使用 filter()方法。

```java
// Java code for DoubleStream filter
// (DoublePredicate predicate) to get a stream
// consisting of the elements of this
// stream that match the given predicate.
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream
        DoubleStream stream = DoubleStream.of(3.6, 5.4, 6.6, 8.1, 9.7);

        // Using DoubleStream filter(DoublePredicate predicate)
        // to get a stream consisting of the
        // elements that are greater than 5.7
        stream.filter(num -> num > 5.7)
            .forEach(System.out::println);
    }
}
```

**Output:**

```java
6.6
8.1
9.7

```

**示例 2 :** 在 DoubleStream 上使用 filter()方法。

```java
// Java code for DoubleStream filter
// (DoublePredicate predicate) to get a stream
// consisting of the elements of this
// stream that match the given predicate.
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream
        DoubleStream stream = DoubleStream.of(3.6, 5.4, 6.6, 8.1, 9.7);

        // Using DoubleStream filter(DoublePredicate 
        // predicate) to get a stream consisting of 
        // the elements that when divided by 2
        // gives quotient > 2.3
        stream.filter(num -> num / 2.0 > 2.3)
            .forEach(System.out::println);
    }
}
```

**Output:**

```java
5.4
6.6
8.1
9.7

```