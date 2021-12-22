# Java 中的 IntStream average()，示例

> 原文:[https://www . geesforgeks . org/int stream-average-in-Java-with-examples/](https://www.geeksforgeeks.org/intstream-average-in-java-with-examples/)

Java 8 中的 java.util.stream.IntStream 处理原语 int。它有助于以一种新的方式解决在数组中寻找最大值、在数组中寻找最小值、在数组中所有元素的和以及在数组中所有值的平均值等老问题。 **IntStream average()** 返回一个描述该流元素算术平均值的 OptionalDouble，如果该流为空，则返回一个空的可选值。

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
// Java code for IntStream average()
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // creating a stream
        IntStream stream = IntStream.of(2, 3, 4, 5, 6, 7, 8);

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

**输出:**

```java
5.0
```

**例 2 :**

## 爪哇

```java
// Implementation of IntStream average()
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // creating a stream
        IntStream stream = IntStream.of(2, 3, 3, 4, 6, 8, 8);

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

**输出:**

```java
4.857142857142857
```