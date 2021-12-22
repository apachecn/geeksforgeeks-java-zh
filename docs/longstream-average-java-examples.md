# Java 中的 LongStream 平均值()，示例

> 原文:[https://www . geesforgeks . org/longstream-average-Java-examples/](https://www.geeksforgeeks.org/longstream-average-java-examples/)

Java 8 中的 java.util.stream.LongStream 处理原始的 Longs。它有助于以一种新的方式解决在数组中寻找最大值、在数组中寻找最小值、在数组中所有元素的和以及在数组中所有值的平均值等老问题。 **LongStream average()** 返回描述该流元素算术平均值的 OptionalDouble，如果该流为空，则返回空的可选值。

**语法:**

```java
OptionalDouble average()

Where, OptionalDouble is a container object 
which may or may not contain a double value.
```

下面给出了一些例子来更好地理解这个函数。

**例 1 :**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code for LongStream average()
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // creating a stream
        LongStream stream = LongStream.of(2L, 3L, 4L,
                                          5L, 6L, 7L, 8L);

        // OptionalDouble is a container object
        // which may or may not contain a
        // double value.
        OptionalDouble obj = stream.average();

        // If a value is present, isPresent() will
        // return true and getAsDouble() will
        // return the value
        if (obj.isPresent()) {
            System.out.println(obj.getAsDouble());
        }
        else {
            System.out.println("-1");
        }
    }
}
```

**Output:** 

```java
5.0
```

**例 2 :**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Implementation of LongStream average()
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // creating a stream
        LongStream stream = LongStream.of(2L, 3L, 3L, 4L, 6L, 8L, 8L);

        // OptionalDouble is a container object
        // which may or may not contain a
        // double value.
        OptionalDouble obj = stream.average();

        // If a value is present, isPresent() will
        // return true and getAsDouble() will
        // return the value
        if (obj.isPresent()) {
            System.out.println(obj.getAsDouble());
        }
        else {
            System.out.println("-1");
        }
    }
}
```

**Output:** 

```java
4.857142857142857
```