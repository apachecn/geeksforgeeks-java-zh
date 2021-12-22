# Java 中的 IntStream min()，示例

> 原文:[https://www.geeksforgeeks.org/intstream-min-java-examples/](https://www.geeksforgeeks.org/intstream-min-java-examples/)

Java 8 中的 java.util.stream.IntStream 处理原语 int。它有助于以一种新的方式解决在数组中寻找最大值、在数组中寻找最小值、在数组中所有元素的和以及在数组中所有值的平均值等老问题。 **IntStream min()** 返回描述该流最小元素的 OptionalInt，如果该流为空，则返回空的 optional int。

**语法:**

```java
OptionalInt() min()

Where, OptionalInt is a container object which 
may or may not contain a int value.

```

下面给出了一些例子来更好地理解这个函数。
**例 1 :**

```java
// Java code for IntStream min()
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
        OptionalInt obj = stream.min();

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
-18

```

**例 2 :**

```java
// Java code for IntStream min()
// to get the minimum value in range
// excluding the last element
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // To find minimum in given range
        IntStream stream = IntStream.range(50, 75);

        // storing the minimum value in variable
        // if it is present, else show -1.
        int minimum = stream.min().orElse(-1);

        // displaying the minimum value
        System.out.println(minimum);
    }
}
```

输出:

```java
50

```

**例 3 :**

```java
// Java code for IntStream min()
// to get the minimum value in range
// excluding the last element
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // To find minimum in given range
        IntStream stream = IntStream.range(50, 50);

        // storing the minimum value in variable
        // if it is present, else show -1.
        int minimum = stream.min().orElse(-1);

        // displaying the minimum value
        System.out.println(minimum);
    }
}
```

输出:

```java
-1

```