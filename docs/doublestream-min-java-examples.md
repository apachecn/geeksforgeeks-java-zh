# Java 中的 DoubleStream min()，示例

> 原文:[https://www . geesforgeks . org/double stream-min-Java-examples/](https://www.geeksforgeeks.org/doublestream-min-java-examples/)

***Java 8 中的 Java . util . stream . double stream***处理原语的双打。它以一种新的方式解决了求数组中的最大值、求数组中的最小值、求数组中所有元素的和、求数组中所有值的平均值等问题。 **DoubleStream min()** 返回描述该流的最小元素的 OptionalDouble，如果该流为空，则返回空的 OptionalDouble。

**语法:**

```java
OptionalDouble() min()

Where, OptionalDouble is a container object which 
may or may not contain a double value.

```

**注:**

1.  与数值比较运算符不同，该方法认为负零严格小于正零。
2.  这是降价的特例。

**例 1 :**

```java
// Java code for DoubleStream min()
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // creating a stream
        DoubleStream stream = DoubleStream.of(-9.5,
                   -18.6, 54.3, 8.5, 7.4, 14.2, 3.9);

        // OptionalDouble is a container object
        // which may or may not contain a
        // double value.
        OptionalDouble obj = stream.min();

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

输出:

```java
-18.6

```

**例 2 :**

```java
// Java code for DoubleStream min()
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // OptionalDouble is a container object
        // which may or may not contain a
        // double value.
        OptionalDouble obj = DoubleStream.empty().min();

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

输出:

```java
-1

```