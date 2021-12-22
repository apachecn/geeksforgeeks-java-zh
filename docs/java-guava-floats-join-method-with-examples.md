# Java 番石榴| Floats.join()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-floats-join-method-with-examples/](https://www.geeksforgeeks.org/java-guava-floats-join-method-with-examples/)

番石榴库中 **[Floats 类](https://www.geeksforgeeks.org/floats-class-guava-java/)** 的 **join()** 方法用于组合或连接由**分隔符**分隔的所有给定的 float 值。这些浮点值被作为参数传递给这个方法。此方法还将分隔符作为参数。此方法返回一个字符串，该字符串是对指定浮点值进行联接操作的结果。

> **例如:**join(“-”、1L、2L、3L)返回字符串“1-2-3”。

**语法:**

> 公共静态字符串连接(字符串分隔符、浮点…数组)

**参数:**该方法接受两个强制参数:

*   **分隔符:**是出现在连接的浮点值之间的浮动字符。
*   **数组:**是要连接的浮点值数组。

**返回值:**这个方法返回一个包含所有给定浮点值的字符串，用*分隔符*分隔。

下面的程序说明了这种方法的使用:

**例 1:**

```java
// Java code to show implementation of
// Guava's Floats.join() method

import com.google.common.primitives.Floats;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a float array
        float[] arr = { 2.3f, 4.2f, 6.2f, 8.6f, 10.5f };

        // Using Floats.join() method to get a
        // string containing the elements of array
        // separated by a separator
        System.out.println(Floats.join("#", arr));
    }
}
```

**Output:**

```java
2.3#4.2#6.2#8.6#10.5

```

**例 2:**

```java
// Java code to show implementation of
// Guava's Floats.join() method

import com.google.common.primitives.Floats;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a float array
        float[] arr = { 3.2f, 5.4f, 7.6f, 9.1f, 11.2f };

        // Using Floats.join() method to get a
        // string containing the elements of array
        // separated by a separator
        System.out.println(Floats.join("*", arr));
    }
}
```

**Output:**

```java
3.2*5.4*7.6*9.1*11.2

```

**参考:**[https://Google . github . io/guava/releases/19.0/API/docs/com/Google/common/primitive/floats . html # join(Java . lang . string，% 20 float……)](https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Floats.html#join(java.lang.String, %20float...))