# Java 中的 LongStream 映射(longunaryooperator mapper)

> 原文:[https://www . geesforgeks . org/longstream-maplongunaryooperator-mapper-Java/](https://www.geeksforgeeks.org/longstream-maplongunaryoperator-mapper-java/)

**LongStream map(longunaryooperator mapper)**返回一个流，该流由给定函数应用于该流元素的结果组成。这是一个*T3T5【中间操作】。这些操作总是偷懒。中间操作在流实例上被调用，在它们完成处理后，它们给出一个流实例作为输出。*

**语法:**

```java
LongStream map(LongUnaryOperator mapper)

```

**参数:**

1.  **LongStream :** 原始长值元素的序列。
2.  **longunaryooperator:**对单个长值操作数进行运算，产生长值结果。
3.  **映射器:**应用于每个元素的无状态函数，该函数返回新的流。

**返回值:** LongStream 映射(LongUnaryOperator mapper)通过应用给定的函数返回一个流。

**例 1 :** 利用 LongStream 映射()得到 LongStream 元素平方的负值。

```java
// Java code for LongStream map
// (LongUnaryOperator mapper) to get a
// stream by applying the given function.
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream1 = LongStream.of(4L, 5L, 6L, 7L);

        // Using LongStream map()
        LongStream stream2 = stream1.map(num -> (-num * num));

        // Displaying the resulting LongStream
        stream2.forEach(System.out::println);
    }
}
```

**Output:**

```java
-16
-25
-36
-49

```

**例 2 :** 利用 LongStream map()得到 LongStream 在给定范围内的一半元素。

```java
// Java code for LongStream map
// (LongUnaryOperator mapper) to get a
// stream by applying the given function.
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream in range [2, 7)
        LongStream stream1 = LongStream.range(2, 7);

        // Using LongStream map()
        LongStream stream2 = stream1.map(num -> (num / 2));

        // Displaying the resulting LongStream
        stream2.forEach(System.out::println);
    }
}
```

**Output:**

```java
1
1
2
2
3

```