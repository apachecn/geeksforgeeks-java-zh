# Java 番石榴| Longs.join()方法带示例

> 原文:[https://www . geesforgeks . org/Java-guava-longs-join-method-with-examples/](https://www.geeksforgeeks.org/java-guava-longs-join-method-with-examples/)

番石榴库中 **[Longs 类](https://www.geeksforgeeks.org/longs-class-guava-java/)** 的 **join()** 方法用于组合或连接所有由**分隔符**分隔的给定长值。这些长值被作为参数传递给这个方法。此方法还将分隔符作为参数。此方法返回一个字符串，该字符串是对指定的长值进行联接操作的结果。

> **例如:**join(“-”、1L、2L、3L)返回字符串“1-2-3”。

**语法:**

> 公共静态字符串连接(字符串分隔符，长…数组)

**参数:**该方法接受两个强制参数:

*   **分隔符:**出现在连接的长值之间的字符。
*   **数组:**是要连接的长值数组。

**返回值:**这个方法返回一个包含所有给定长值的字符串，用*分隔符*隔开。

下面的程序说明了这种方法的使用:

**例 1:**

```
// Java code to show implementation of
// Guava's Longs.join() method

import com.google.common.primitives.Longs;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a long array
        long[] arr = { 2, 4, 6, 8, 10 };

        // Using Longs.join() method to get a
        // string containing the elements of array
        // separated by a separator
        System.out.println(Longs.join("#", arr));
    }
}
```

**Output:**

```
2#4#6#8#10

```

**例 2:**

```
// Java code to show implementation of
// Guava's Longs.join() method

import com.google.common.primitives.Longs;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a long array
        long[] arr = { 3, 5, 7, 9, 11 };

        // Using Longs.join() method to get a
        // string containing the elements of array
        // separated by a separator
        System.out.println(Longs.join("*", arr));
    }
}
```

**Output:**

```
3*5*7*9*11

```

**参考:**[https://Google . github . io/guava/releases/21.0/API/docs/com/Google/common/primitive/longs . html # join-Java . lang . string-long……-](https://google.github.io/guava/releases/21.0/api/docs/com/google/common/primitives/Longs.html#join-java.lang.String-long...-)