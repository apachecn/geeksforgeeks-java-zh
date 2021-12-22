# 双流查找第一个()示例

> 原文:[https://www . geesforgeks . org/double stream-find first-examples/](https://www.geeksforgeeks.org/doublestream-findfirst-examples/)

**DoubleStream findFirst()** 返回一个**optionalduble**(可能包含也可能不包含非空值的容器对象)，描述该流的 **first** 元素，如果该流为空，则返回一个空的 optionalduble。

**语法:**

```java
OptionalDouble findFirst()

```

**参数:**

1.  **optionalduble:**可能包含也可能不包含非空值的容器对象。

**返回值:**函数返回一个描述该流第一个元素的 optionalduble，如果该流为空，则返回一个空的 optionalduble。

**注意:** findFirst()是一个 ***端子-短路*** 操作的 Stream 界面。此方法返回满足中间操作的任何第一个元素。

**示例 1 :** 在双流上查找 First()方法。

```java
// Java code for DoubleStream findFirst()
// which returns an OptionalDouble describing
// first element of the stream, or an
// empty OptionalDouble if the stream is empty.
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream
        DoubleStream stream = DoubleStream.of(6.2, 7.3, 8.4, 9.5);

        // Using DoubleStream findFirst() to return
        // an OptionalDouble describing first element
        // of the stream
        OptionalDouble answer = stream.findFirst();

        // if the stream is empty, an empty
        // OptionalDouble is returned.
        if (answer.isPresent())
            System.out.println(answer.getAsDouble());
        else
            System.out.println("no value");
    }
}
```

输出:

```java
6.2

```

**注意:**如果流没有相遇顺序，那么可以返回任何元素。

**示例 2 :** findFirst()方法返回第一个可被 4 整除的元素。

```java
// Java code for DoubleStream findFirst()
// which returns an OptionalDouble describing
// first element of the stream, or an
// empty OptionalDouble if the stream is empty.
import java.util.OptionalDouble;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream
        DoubleStream stream = DoubleStream.of(4.7, 4.5, 
                    8.0, 10.2, 12.0, 16.0).parallel();

        // Using DoubleStream findFirst().
        // Executing the source code multiple times
        // must return the same result.
        // Every time you will get the same
        // Double value which is divisible by 4.
        stream = stream.filter(num -> num % 4.0 == 0);

        OptionalDouble answer = stream.findFirst();
        if (answer.isPresent())
            System.out.println(answer.getAsDouble());
    }
}
```

输出:

```java
8.0

```