# Java 番石榴| Booleans.join()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-booleans-join-method-with-examples/](https://www.geeksforgeeks.org/java-guava-booleans-join-method-with-examples/)

番石榴库中 **[布尔类](https://www.geeksforgeeks.org/booleans-class-guava-java/)** 的 **join()** 方法用于组合或连接所有由**分隔符**分隔的给定布尔值。这些布尔值被传递给这个方法一个参数。此方法还将分隔符作为参数。此方法返回一个字符串，该字符串是对指定的布尔值进行联接操作的结果。

**例如:**join(“-”、false、true、false)返回字符串“false-true-false”。

**语法:**

```
public static String join(String separator,
                          boolean... array)

```

**参数:**该方法接受两个强制参数:

*   **分隔符:**出现在连接的布尔值之间的字符
*   **数组:**是要连接的布尔值数组。

**返回值:**该方法返回一个包含所有给定布尔值的字符串，这些值由*分隔符*分隔。

下面的程序说明了这种方法的使用:

**示例-1 :**

```
// Java code to show implementation of
// Guava's Booleans.join() method

import com.google.common.primitives.Booleans;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating a boolean array
        boolean[] arr = { true, false, true,
                          false, true };

        // Using Booleans.join() method to get a
        // string containing the elements of array
        // separated by a separator
        System.out.println(Booleans.join("#", arr));
    }
}
```

**输出:**

```
true#false#true#false#true

```

**例 2 :**

```
// Java code to show implementation of
// Guava's Booleans.join() method

import com.google.common.primitives.Booleans;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating a boolean array
        boolean[] arr = { false, false,
                          true, false };

        // Using Booleans.join() method to get a
        // string containing the elements of array
        // separated by a separator
        System.out.println(Booleans.join("*", arr));
    }
}
```

**输出:**

```
false*false*true*false

```

**参考:**[https://Google . github . io/guava/releases/20.0/API/docs/com/Google/common/primitive/booleans . html # join-Java . lang . string-boolean……-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/primitives/Booleans.html#join-java.lang.String-boolean...-)