# Java 番石榴| Chars.concat()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-chars-concat-method-with-examples/](https://www.geeksforgeeks.org/java-guava-chars-concat-method-with-examples/)

番石榴库中[字符类](https://www.geeksforgeeks.org/chars-class-guava-java/)的 **concat()** 方法用于将多个数组的值连接成一个数组。这些要连接的字符数组被指定为此方法的参数。

> **例如:** concat(new char[] {a，b}、new char[] {}、new char[] {c}
> 返回数组{a，b，c}。

**语法:**

```java
public static char[] concat(char[]... arrays)

```

**参数:**该方法接受**数组**作为参数，该参数是该方法要连接的字符数组。

**返回值:**该方法返回一个单字符数组，该数组包含所有指定字符数组值的原始顺序。

下面的程序说明了 concat()方法的使用:

**例 1:**

```java
// Java code to show implementation of
// Guava's Chars.concat() method

import com.google.common.primitives.Chars;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating 2 Character arrays
        char[] arr1 = { 'H', 'E', 'L', 'L', 'O' };
        char[] arr2 = { 'G', 'E', 'E', 'K', 'S' };

        // Using Chars.concat() method to combine
        // elements from both arrays into a single array
        char[] res = Chars.concat(arr1, arr2);

        // Displaying the single combined array
        System.out.println(Arrays.toString(res));
    }
}
```

**Output:**

```java
[H, E, L, L, O, G, E, E, K, S]

```

**例 2:**

```java
// Java code to show implementation of
// Guava's Chars.concat() method

import com.google.common.primitives.Chars;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating 4 Character arrays
        char[] arr1 = { '1', '2', '3' };
        char[] arr2 = { '4', '5' };
        char[] arr3 = { '6', '7', '8' };
        char[] arr4 = { '9', '0' };

        // Using Chars.concat() method to combine
        // elements from both arrays into a single array
        char[] res = Chars.concat(arr1, arr2, arr3, arr4);

        // Displaying the single combined array
        System.out.println(Arrays.toString(res));
    }
}
```

**Output:**

```java
[1, 2, 3, 4, 5, 6, 7, 8, 9, 0]

```

**参考:**