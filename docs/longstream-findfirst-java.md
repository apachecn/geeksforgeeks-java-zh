# Java 中的 LongStream findFirst()

> 原文:[https://www.geeksforgeeks.org/longstream-findfirst-java/](https://www.geeksforgeeks.org/longstream-findfirst-java/)

**LongStream findFirst()** 返回描述该流的 **first** 元素的 **OptionalLong** (可能包含也可能不包含非空值的容器对象)，如果该流为空，则返回空 OptionalLong

**语法:**

```java
OptionalLong findFirst()

```

**参数:**

1.  **选项龙:**可能包含也可能不包含非空值的容器对象。

**返回值:**该函数返回描述该流第一个元素的选项龙，如果该流为空，则返回空的选项龙。

**注意:** findAny()是一个 ***端子-短路*** 操作的 Stream 界面。此方法返回满足中间操作的任何第一个元素。

**例 1 :** 在长流上查找 First()方法。

```java
// Java code for LongStream findFirst()
// which returns an OptionalLong describing
// first element of the stream, or an
// empty OptionalLong if the stream is empty.
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream = LongStream.of(6L, 7L, 8L, 9L);

        // Using LongStream findFirst() to return
        // an OptionalLong describing first element
        // of the stream
        OptionalLong answer = stream.findFirst();

        // if the stream is empty, an empty
        // OptionalLong is returned.
        if (answer.isPresent())
            System.out.println(answer.getAsLong());
        else
            System.out.println("no value");
    }
}
```

输出:

```java
6

```

**注意:**如果流没有相遇顺序，那么可以返回任何元素。

**示例 2 :** findFirst()方法返回第一个可被 4 整除的元素。

```java
// Java code for LongStream findFirst()
// which returns an OptionalLong describing
// first element of the stream, or an
// empty OptionalLong if the stream is empty.
import java.util.OptionalLong;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream = LongStream.of(4L, 5L, 8L, 10L, 12L, 16L)
                                .parallel();

        // Using LongStream findFirst().
        // Executing the source code multiple times
        // must return the same result.
        // Every time you will get the same
        // value which is divisible by 4.
        stream = stream.filter(num -> num % 4 == 0);

        OptionalLong answer = stream.findFirst();
        if (answer.isPresent())
            System.out.println(answer.getAsLong());
    }
}
```

输出:

```java
4

```