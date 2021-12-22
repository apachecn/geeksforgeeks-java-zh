# Java 中的 LongStream distinct()，示例

> 原文:[https://www . geesforgeks . org/longstream-distinct-Java-examples/](https://www.geeksforgeeks.org/longstream-distinct-java-examples/)

**LongStream distinct()** 是 java.util.stream.LongStream 中的一个方法，这个方法返回一个由 distinct 元素组成的流。这是一个 ***有状态的中间操作*** ，也就是说，在处理新元素时，它可能会包含来自以前看到的元素的状态。

**语法:**

```
LongStream distinct()

Where, LongStream is a sequence of 
primitive long-valued elements.

```

下面给出了一些例子来更好地理解这个函数。
**例 1 :** 印刷龙溪的鲜明元素。

```
// Java code for LongStream distinct()
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // creating a stream
        LongStream stream = LongStream.of(2L, 3L,
                              3L, 5L, 6L, 6L, 8L);

        // Displaying only distinct elements
        // using the distinct() method
        stream.distinct().forEach(System.out::println);
    }
}
```

**Output:**

```
2
3
5
6
8

```

**示例 2 :** 计算流中不同元素的值。

```
// Java code for LongStream distinct() method
// to count the number of distinct
// elements in given stream
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // creating a stream
        LongStream stream = LongStream.of(2L, 3L, 3L,
                                      5L, 6L, 6L, 8L);

        // storing the count of distinct elements
        // in a variable named total
        long total = stream.distinct().count();

        // displaying the total number of elements
        System.out.println(total);
    }
}
```

**Output:**

```
5

```