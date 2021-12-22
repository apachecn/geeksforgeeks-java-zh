# Java 中的 LongStream count()，示例

> 原文:[https://www . geesforgeks . org/longstream-count-Java-examples/](https://www.geeksforgeeks.org/longstream-count-java-examples/)

**LongStream count()** 返回流中元素的计数。LongStream count()存在于 Java . util . stream . LongStream
**语法:**

```java
long count()

```

**例 1 :** 计算 LongStream 中的元素。

```java
// Java code for LongStream count()
// to count the number of elements in
// given stream
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // creating a stream
        LongStream stream = LongStream.of(2L, 3L, 4L, 5L,
                                          6L, 7L, 8L);

        // storing the count of elements
        // in a variable named total
        long total = stream.count();

        // displaying the total number of elements
        System.out.println(total);
    }
}
```

**Output:**

```java
7

```

**例 2 :** 统计给定范围内的元素。

```java
// Java code for LongStream count()
// to count the number of elements in
// given range excluding the last element
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // creating a stream
        LongStream stream = LongStream.range(2, 50);

        // storing the count of elements
        // in a variable named total
        long total = stream.count();

        // displaying the total number of elements
        System.out.println(total);
    }
}
```

**Output:**

```java
48

```

**例 3 :** 计算 LongStream 中不同的元素。

```java
// Java code for LongStream count()
// to count the number of distinct
// elements in given stream
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // creating a stream
        LongStream stream = LongStream.of(2L, 3L, 4L, 4L,
                                          7L, 7L, 8L);

        // storing the count of distinct elements
        // in a variable named total
        long total = stream.distinct().count();

        // displaying the total number of elements
        System.out.println(total);
    }
}
```

**Output:**

```java
5

```