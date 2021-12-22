# Java 番石榴| Booleans.countTrue()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-booleans-count true-method-with-examples/](https://www.geeksforgeeks.org/java-guava-booleans-counttrue-method-with-examples/)

番石榴库中 **[布尔类](https://www.geeksforgeeks.org/booleans-class-guava-java/)** 的 **countTrue()** 方法用于计算作为参数传递的指定布尔值中为真的值的数量。

**语法:**

```java
public static int countTrue(boolean... values)

```

**参数:**该方法接受**布尔值**，其中真值要计数。

**返回值:**该方法返回一个整数值，即真值的计数。

**示例-1 :**

```java
// Java code to show implementation of
// Guava's Booleans.countTrue() method

import com.google.common.primitives.Booleans;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a Boolean array
        boolean[] arr = { false, true, false,
                          true, true };

        // Using Booleans.countTrue() method to
        // get the number of values that are true
        System.out.println(Booleans.countTrue(arr));
    }
}
```

**输出:**

```java
3

```

**例 2 :**

```java
// Java code to show implementation of
// Guava's Booleans.countTrue() method

import com.google.common.primitives.Booleans;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating a Boolean array
        boolean[] arr = { false, false,
                          false, false };

        // Using Booleans.countTrue() method to
        // get the number of values that are true
        System.out.println(Booleans.countTrue(arr));
    }
}
```

**输出:**

```java
0

```

**参考:**[https://Google . github . io/guava/releases/20.0/API/docs/com/Google/common/primitive/booleans . html # countrtrue-boolean……-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/primitives/Booleans.html#countTrue-boolean...-)