# Java 中的 IntStream max()，示例

> 原文:[https://www . geesforgeks . org/int stream-max-in-Java-with-examples/](https://www.geeksforgeeks.org/intstream-max-in-java-with-examples/)

Java 8 中的 java.util.stream.IntStream 处理原语 int。它以一种新的方式解决了求数组中的最大值、求数组中的最小值、求数组中所有元素的和、求数组中所有值的平均值等问题。 **IntStream max()** 返回描述该流最大元素的 OptionalInt，如果该流为空，则返回空的 optional int。

**语法:**

```java
OptionalInt() max()

Where, OptionalInt is a container object which 
may or may not contain a int value.

```

**例 1 :**

```java
// Java code for IntStream max()
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // creating a stream
        IntStream stream = IntStream.of(-9, -18, 54, 8, 7, 14, 3);

        // OptionalInt is a container object
        // which may or may not contain a
        // int value.
        OptionalInt obj = stream.max();

        // If a value is present, isPresent() will
        // return true and getAsInt() will
        // return the value
        if (obj.isPresent()) {
            System.out.println(obj.getAsInt());
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
// Java code for IntStream max()
// to get the maximum value in range
// excluding the last element
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // To find maximum in given range
        IntStream stream = IntStream.range(50, 75);

        // storing the maximum value in variable
        // if it is present, else show -1.
        int maximum = stream.max().orElse(-1);

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
// Java code for IntStream max()
// to get the maximum value in range
// excluding the last element
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // To find maximum in given range
        IntStream stream = IntStream.range(50, 50);

        // storing the maximum value in variable
        // if it is present, else show -1.
        int maximum = stream.max().orElse(-1);

        // displaying the maximum value
        System.out.println(maximum);
    }
}
```

输出:

```java
-1

```