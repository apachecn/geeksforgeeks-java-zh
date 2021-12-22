# Java 中的 IntStream count()，示例

> 原文:[https://www . geesforgeks . org/int stream-count-in-Java-with-examples/](https://www.geeksforgeeks.org/intstream-count-in-java-with-examples/)

**IntStream count()** 返回流中元素的计数。IntStream count()在 java.util.stream.IntStream 中存在
T3】语法:

```java
long count()

```

**例 1 :** 统计 IntStream 中的元素。

```java
// Java code for IntStream count()
// to count the number of elements in
// given stream
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // creating a stream
        IntStream stream = IntStream.of(2, 3, 4, 5, 6, 7, 8);

        // storing the count of elements
        // in a variable named total
        long total = stream.count();

        // displaying the total number of elements
        System.out.println(total);
    }
}
```

输出:

```java
7

```

**例 2 :** 统计给定范围内的元素。

```java
// Java code for IntStream count()
// to count the number of elements in
// given range excluding the last element
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // creating a stream
        IntStream stream = IntStream.range(2, 50);

        // storing the count of elements
        // in a variable named total
        long total = stream.count();

        // displaying the total number of elements
        System.out.println(total);
    }
}
```

输出:

```java
48

```

**示例 3 :** 计算 IntStream 中的不同元素。

```java
// Java code for IntStream count()
// to count the number of distinct
// elements in given stream
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // creating a stream
        IntStream stream = IntStream.of(2, 3, 4, 4, 7, 7, 8);

        // storing the count of distinct elements
        // in a variable named total
        long total = stream.distinct().count();

        // displaying the total number of elements
        System.out.println(total);
    }
}
```

输出:

```java
5

```