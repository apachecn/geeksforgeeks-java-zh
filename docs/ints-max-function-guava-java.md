# Ints max()函数|番石榴| Java

> 原文:[https://www.geeksforgeeks.org/ints-max-function-guava-java/](https://www.geeksforgeeks.org/ints-max-function-guava-java/)

番石榴的**T1Ints。max()** 返回数组中出现的 ***最大*** 值。

**语法:**

```java
public static int max(int... array)

```

**参数:**该方法以 ***数组*** 为参数，该参数为 *int* 值的非空数组。

**返回值:**该方法返回数组中大于或等于数组中其他值的值*。*

**异常:**阵为空则法掷***IllegalArgumentException***。

以下示例说明了 Ints.max()方法:

**例 1:**

```java
// Java code to show implementation of
// Guava's Ints.max() method

import com.google.common.primitives.Ints;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating an integer array
        int[] arr = { 2, 4, 6, 10, 0, -5, 15, 7 };

        // Using Ints.max() method to get the
        // maximum value present in the array
        System.out.println("Maximum value is: "
                           + Ints.max(arr));
    }
}
```

**输出:**

```java
Maximum value is: 15

```

**示例 2:** 演示 IllegalArgumentException

```java
// Java code to show implementation of
// Guava's Ints.max() method

import com.google.common.primitives.Ints;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        try {
            // Creating an integer array
            int[] arr = {};

            // Using Ints.max() method to get the
            // maximum value present in the array
            // This should raise "IllegalArgumentException"
            // as the array is empty
            System.out.println("Maximum value is: "
                               + Ints.max(arr));
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```java
Exception: java.lang.IllegalArgumentException

```

**参考:**[https://Google . github . io/guava/releases/22.0/API/docs/com/Google/common/primitives/ints . html # max-int……-](https://google.github.io/guava/releases/22.0/api/docs/com/google/common/primitives/Ints.html#max-int...-)