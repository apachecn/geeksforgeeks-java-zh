# 双流查找任意()带示例

> 原文:[https://www . geesforgeks . org/double stream-find any-examples/](https://www.geeksforgeeks.org/doublestream-findany-examples/)

**DoubleStream findAny()** 返回一个描述流的某个元素的**optionalduble**(一个容器对象，可以包含也可以不包含非空值)，如果流为空，则返回一个空的 optionalduble。

**语法:**

```java
OptionalDouble findAny()

```

**参数:**

1.  **optionalduble:**可能包含也可能不包含非空值的容器对象。

**返回值:**该函数返回一个描述该流的某个元素的 optionalduble，如果该流为空，则返回一个空的 optionalduble。

**注意:** findAny()是一个 ***端子-短路*** 操作的 Stream 界面。此方法返回满足中间操作的任何第一个元素。这是一个短路操作，因为它只需要返回**‘any’**第一个元素，并终止剩余的迭代。

**例 1 :** 在双流上找到任意()方法。

```java
// Java code for DoubleStream findAny()
// which returns an OptionalDouble describing
// some element of the stream, or an
// empty OptionalDouble if the stream is empty.
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream
        DoubleStream stream = DoubleStream.of(6.3, 7.4, 8.5, 9.6);

        // Using DoubleStream findAny() to return
        // an OptionalDouble describing some element
        // of the stream
        OptionalDouble answer = stream.findAny();

        // if the stream is empty, an empty
        // OptionalDouble is returned.
        if (answer.isPresent()) {
            System.out.println(answer.getAsDouble());
        }
        else {
            System.out.println("no value");
        }
    }
}
```

输出:

```java
6.3

```

**注意:**double stream find any()操作的行为是显式的**非确定性的**，即可以自由选择流中的任意元素。对同一源的多次调用可能不会返回相同的结果。

**示例 2 :** findAny()方法以非确定性方式返回可被 4 整除的元素。

```java
// Java code for DoubleStream findAny()
// which returns an OptionalDouble describing
// some element of the stream, or an
// empty OptionalDouble if the stream is empty.
import java.util.OptionalDouble;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream
        DoubleStream stream = DoubleStream.of(4.4, 5.6,
                    8.4, 10.2, 12.0, 16.0).parallel();

        // Using DoubleStream findAny().
        // Executing the source code multiple times
        // may not return the same result.
        // Every time you may get a different
        // Double value which is divisible by 4.
        stream = stream.filter(num -> num % 4 == 0);

        OptionalDouble answer = stream.findAny();
        if (answer.isPresent()) {
            System.out.println(answer.getAsDouble());
        }
    }
}
```

输出:

```java
16.0

```