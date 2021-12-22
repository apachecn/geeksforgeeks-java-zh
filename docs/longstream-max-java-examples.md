# Java 中的 LongStream max()，示例

> 原文:[https://www.geeksforgeeks.org/longstream-max-java-examples/](https://www.geeksforgeeks.org/longstream-max-java-examples/)

Java 8 中的 java.util.stream.LongStream 处理原语 longs。它以一种新的方式帮助解决了求数组中最大值、求数组中最小值、求数组中所有元素的和、求数组中所有值的平均值等问题。 **LongStream max()** 返回一个描述该流的**最大值**元素的可选值，如果该流为空，则返回一个空的可选值。

**语法:**

```java
OptionalLong() max()

Where, OptionalLong is a container object which 
may or may not contain a long value.

```

**例 1 :**

```java
// Java code for LongStream max()
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // creating a stream
        LongStream stream = LongStream.of(-9L, -18L, 54L,
                                          8L, 7L, 14L, 3L);

        // OptionalLong is a container object
        // which may or may not contain a
        // long value.
        OptionalLong obj = stream.max();

        // If a value is present, isPresent() will
        // return true and getAsLong() will
        // return the value
        if (obj.isPresent()) {
            System.out.println(obj.getAsLong());
        }
        else {
            System.out.println("-1");
        }
    }
}
```

输出:

```java
54

```

**例 2 :**

```java
// Java code for LongStream max()
// to get the maximum value in range
// excluding the last element
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // To find maximum in given range
        LongStream stream = LongStream.range(50L, 75L);

        // storing the maximum value in variable
        // if it is present, else show -1.
        long maximum = stream.max().orElse(-1);

        // displaying the maximum value
        System.out.println(maximum);
    }
}
```

输出:

```java
74

```

**例 3 :**

```java
// Java code for LongStream max()
// to get the maximum value in range
// excluding the last element
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // To find maximum in given range
        LongStream stream = LongStream.range(50L, 50L);

        // storing the maximum value in variable
        // if it is present, else show -1.
        long maximum = stream.max().orElse(-1);

        // displaying the maximum value
        System.out.println(maximum);
    }
}
```

输出:

```java
-1

```