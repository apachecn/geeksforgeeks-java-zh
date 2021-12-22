# 爪哇番石榴| Doubles.join()方法示例

> 原文:[https://www . geesforgeks . org/Java-guava-double-join-method-with-examples/](https://www.geeksforgeeks.org/java-guava-doubles-join-method-with-examples/)

番石榴库中 **[双打类](https://www.geeksforgeeks.org/doubles-class-guava-java/)** 的 **join()** 方法用于组合或连接由**分隔符**分隔的所有给定的双打值。这些双精度值被传递给这个方法一个参数。此方法还将分隔符作为参数。此方法返回一个字符串，该字符串是对指定的双精度值进行连接操作的结果。

> **例如:**join(“-”、1L、2L、3L)返回字符串“1-2-3”。

**语法:**

> 公共静态字符串连接(字符串分隔符，双…数组)

**参数:**该方法接受两个强制参数:

*   **分隔符:**是出现在连接的双精度值之间的双精度符。
*   **数组:**是要连接的双精度值数组。

**返回值:**这个方法返回一个包含所有给定双精度值的字符串，用*分隔符*分隔。

下面的程序说明了这种方法的使用:

**例 1:**

```
// Java code to show implementation of
// Guava's Doubles.join() method

import com.google.common.primitives.Doubles;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a double array
        double[] arr = { 2.3, 4.2, 6.2, 8.6, 10.5 };

        // Using Doubles.join() method to get a
        // string containing the elements of array
        // separated by a separator
        System.out.println(Doubles.join("#", arr));
    }
}
```

**Output:**

```
2.3#4.2#6.2#8.6#10.5

```

**例 2:**

```
// Java code to show implementation of
// Guava's Doubles.join() method

import com.google.common.primitives.Doubles;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a double array
        double[] arr = { 3.2, 5.4, 7.6, 9.1, 11.2 };

        // Using Doubles.join() method to get a
        // string containing the elements of array
        // separated by a separator
        System.out.println(Doubles.join("*", arr));
    }
}
```

**Output:**

```
3.2*5.4*7.6*9.1*11.199999809265137

```

**参考:**[https://Google . github . io/guava/releases/19.0/API/docs/com/Google/common/primitive/double . html # join(Java . lang . string，% 20 double……)](https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Doubles.html#join(java.lang.String, %20double...))