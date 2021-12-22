# Java 番石榴|短裤. join()方法带示例

> 原文:[https://www . geesforgeks . org/Java-guava-shots-join-method-with-examples/](https://www.geeksforgeeks.org/java-guava-shorts-join-method-with-examples/)

**短裤. join()** 是番石榴库中[短裤类](https://www.geeksforgeeks.org/shorts-class-guava-java/)的一种方法，它返回由 ***分隔符*** 分隔的所有给定短值的组合字符串。例如，join(“-”、(short) 1、(short) 2、(short) 3)返回字符串“1-2-3”。

**语法:**

```java
public static String join(String separator,
                          short... array)

```

**参数:**

*   **Separator:** Text that should appear between consecutive values in the result string (but not at the beginning or end).
*   **Array:** A short array of *values, which may be empty.*

**返回值:**包含由*分隔符*分隔的短值的字符串。

**示例-1:**

```java
// Java code to show implementation of
// Guava's Shorts.join() method
import com.google.common.primitives.Shorts;
import java.util.Arrays;

class GFG {
    // Driver's code
    public static void main(String[] args)
    {
        // Creating a short array
        short[] arr = { 2, 4, 6, 8, 10 };

        // Using Shorts.join() method to get a
        // string containing the elements of array
        // separated by a separator
        System.out.println(Shorts.join("#", arr));
    }
}
```

**输出:**

```java
2#4#6#8#10

```

**示例-2:**

```java
// Java code to show implementation of
// Guava's Shorts.join() method
import com.google.common.primitives.Shorts;
import java.util.Arrays;

class GFG {
    // Driver's code
    public static void main(String[] args)
    {
        // Creating a short array
        short[] arr = { 3, 5, 7, 9, 11 };

        // Using Shorts.join() method to get a
        // string containing the elements of array
        // separated by a separator
        System.out.println(Shorts.join("*", arr));
    }
}
```

**输出:**

```java
3*5*7*9*11

```

**参考:**[https://Google . github . io/guava/releases/23.0/API/docs/com/Google/common/primitive/短裤. html # join-Java . lang . string-short……-](https://google.github.io/guava/releases/23.0/api/docs/com/google/common/primitives/Shorts.html#join-java.lang.String-short...-)