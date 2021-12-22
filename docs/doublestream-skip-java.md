# Java 中的 DoubleStream skip()

> 原文:[https://www.geeksforgeeks.org/doublestream-skip-java/](https://www.geeksforgeeks.org/doublestream-skip-java/)

**双流跳过(长 n)** 在丢弃流的第 n 个**元素后，返回由该流的剩余元素组成的流。如果此流包含的元素少于 n 个，则将返回一个空流。**

**注意:** DoubleStream skip()是一个 ***有状态的中间操作*** ，也就是说，在处理新元素时，它可能会合并来自之前看到的元素的状态。有状态的中间操作可能需要在产生结果之前处理整个输入。例如，在看到流的所有元素之前，无法对流进行排序。

**语法:**

```java
DoubleStream skip(long n)

```

**参数:**

1.  **双流:**原始双值元素的序列。这就是[流](https://www.geeksforgeeks.org/stream-in-java/)的双原始特化。
2.  **n :** 要跳过的前导元素数量。

**返回值:**函数丢弃前 n 个元素后返回新的流。

**异常:**如果 n 为负，函数抛出***IllegalArgumentException***。

**例 1 :**

```java
// Java code for DoubleStream skip() function
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a DoubleStream
        DoubleStream stream = 
            DoubleStream.of(5.5, 2.6, 4.6, 7.0, 13.2, 15.4);

        // Using skip() to skip first 3 values in DoubleStream
        // and displaying the rest of elements
        stream.skip(3).forEach(System.out::println);
    }
}
```

**Output:**

```java
7.0
13.2
15.4

```

**例 2 :**

```java
// Java code for DoubleStream skip() function
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a DoubleStream
        DoubleStream stream =
           DoubleStream.of(5.5, 2.6, 4.6, 7.0, 13.2, 15.4);

        // Using parallel skip() to skip first 3 values in range
        // and displaying the rest of elements
        stream.parallel().skip(3).forEach(System.out::println);
    }
}
```

**Output:**

```java
13.2
7.0
15.4

```