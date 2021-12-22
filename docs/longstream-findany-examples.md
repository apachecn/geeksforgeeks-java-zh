# LongStream findAny()带示例

> 原文:[https://www.geeksforgeeks.org/longstream-findany-examples/](https://www.geeksforgeeks.org/longstream-findany-examples/)

**LongStream findAny()** 返回一个**选项龙**(一个可能包含也可能不包含非空值的容器对象)来描述流的某个元素，如果流为空，则返回一个空选项龙。

**语法:**

```java
OptionalLong findAny() 

```

**参数:**

1.  **选项龙:**可能包含也可能不包含非空值的容器对象。

**返回值:**该函数返回一个描述该流的某个元素的选项龙，如果该流为空，则返回一个空的选项龙。

**注意:** findAny()是一个 ***端子-短路*** 操作的 Stream 界面。此方法返回满足中间操作的任何第一个元素。这是一个短路操作，因为它只需要返回**‘any’**第一个元素，并终止剩余的迭代。

**例 1 :** 在长流上找到任意()方法。

```java
// Java code for LongStream findAny()
// which returns an OptionalLong describing
// some element of the stream, or an
// empty OptionalLong if the stream is empty.
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream = LongStream.of(6L, 7L, 8L, 9L);

        // Using LongStream findAny() to return
        // an OptionalLong describing some element
        // of the stream
        OptionalLong answer = stream.findAny();

        // if the stream is empty, an empty
        // OptionalLong is returned.
        if (answer.isPresent()) {
            System.out.println(answer.getAsLong());
        }
        else {
            System.out.println("no value");
        }
    }
}
```

输出:

```java
6

```

**注意:**LongStream find any()操作的行为是显式的**非确定性的**即可以自由选择流中的任意元素。对同一源的多次调用可能不会返回相同的结果。

**示例 2 :** findAny()方法以非确定性方式返回可被 4 整除的元素。

```java
// Java code for LongStream findAny()
// which returns an OptionalLong describing
// some element of the stream, or an
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

        // Using LongStream findAny().
        // Executing the source code multiple times
        // may not return the same result.
        // Every time you may get a different
        // value which is divisible by 4.
        stream = stream.filter(num -> num % 4 == 0);

        OptionalLong answer = stream.findAny();
        if (answer.isPresent()) {
            System.out.println(answer.getAsLong());
        }
    }
}
```

输出:

```java
16

```