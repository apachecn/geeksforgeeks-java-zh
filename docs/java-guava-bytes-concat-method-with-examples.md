# Java 番石榴| Bytes.concat()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-bytes-concat-method-with-examples/](https://www.geeksforgeeks.org/java-guava-bytes-concat-method-with-examples/)

番石榴库中[字节类](https://www.geeksforgeeks.org/bytes-class-guava-java/)的 **concat()** 方法用于将多个数组的值连接成一个数组。这些要连接的字节数组被指定为此方法的参数。

> **例如:** concat(新字节[] {1，2}，新字节[] {3，4，5}，新字节[] {6，7}
> 返回数组{1，2，3，4，5，6，7}。

**语法:**

```java
public static byte[] concat(byte[]... arrays)

```

**参数:**该方法接受**数组**作为参数，该参数是该方法要连接的字节数组。

**返回值:**该方法返回一个单字节数组，该数组包含所有指定字节数组值的原始顺序。

下面的程序说明了 concat()方法的使用:

**例 1:**

```java
// Java code to show implementation of
// Guava's Bytes.concat() method

import com.google.common.primitives.Bytes;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating 2 Byte arrays
        byte[] arr1 = { 1, 2, 3, 4, 5 };
        byte[] arr2 = { 6, 2, 7, 0, 8 };

        // Using Bytes.concat() method to combine
        // elements from both arrays into a single array
        byte[] res = Bytes.concat(arr1, arr2);

        // Displaying the single combined array
        System.out.println(Arrays.toString(res));
    }
}
```

**Output:**

```java
[1, 2, 3, 4, 5, 6, 2, 7, 0, 8]

```

**例 2:**

```java
// Java code to show implementation of
// Guava's Bytes.concat() method

import com.google.common.primitives.Bytes;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating 4 byte arrays
        byte[] arr1 = { 1, 2, 3 };
        byte[] arr2 = { 4, 5 };
        byte[] arr3 = { 6, 7, 8 };
        byte[] arr4 = { 9, 0 };

        // Using Bytes.concat() method to combine
        // elements from both arrays into a single array
        byte[] res = Bytes.concat(arr1, arr2, arr3, arr4);

        // Displaying the single combined array
        System.out.println(Arrays.toString(res));
    }
}
```

**Output:**

```java
[1, 2, 3, 4, 5, 6, 7, 8, 9, 0]

```

**参考:**[https://Google . github . io/guava/releases/19.0/API/docs/com/Google/common/primitives/bytes . html # concat(byte[]……)](https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Bytes.html#concat(byte[]...))