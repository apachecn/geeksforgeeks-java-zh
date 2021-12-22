# Java 番石榴| Bytes.lastIndexOf()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-bytes-last indexof-method-with-examples/](https://www.geeksforgeeks.org/java-guava-bytes-lastindexof-method-with-examples/)

番石榴库中 **[字节类](https://www.geeksforgeeks.org/bytes-class-guava-java/)** 的 **lastIndexOf()** 方法用于查找字节数组中给定字节值的最后一个索引。要搜索的字节值和要搜索的字节数组都作为参数传递给此方法。它返回一个整数值，这是指定字节值的最后一个索引。如果找不到该值，它将返回-1。

**语法:**

```java
public static int lastIndexOf(byte[] array,
                              byte target)

```

**参数:**该方法接受两个强制参数:

*   **Array:** is the byte value array to search for byte values.
*   **Target:** is the byte value to be searched by the last index in the byte array.

**返回值:**该方法返回一个整数值，该整数值是指定字节值的最后一个索引。如果找不到该值，它将返回-1。

下面的程序说明了这种方法:

**例 1:**

```java
// Java code to show implementation of
// Guava's Bytes.lastIndexOf() method

import com.google.common.primitives.Bytes;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a byte array
        byte[] arr = { 1, 2, 3, 4, 3, 5, 3, 4 };

        byte target = 3;

        // Using Bytes.lastIndexOf() method
        // to get the index of last appearance
        // of a given element in array
        // and return -1 if element is
        // not found in the array
        int index
            = Bytes.lastIndexOf(arr, target);

        if (index != -1) {
            System.out.println("Target is present"
                               + " at index "
                               + index);
        }
        else {
            System.out.println("Target is not present"
                               + " in the array");
        }
    }
}
```

**输出:**

```java
Target is present at index 6

```

**例 2:**

```java
// Java code to show implementation of
// Guava's Bytes.lastIndexOf() method

import com.google.common.primitives.Bytes;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating a byte array
        byte[] arr = { 3, 5, 7, 11, 13 };

        byte target = 17;

        // Using Bytes.lastIndexOf() method
        // to get the index of last appearance
        // of a given element in array
        // and return -1 if element is
        // not found in the array
        int index
            = Bytes.lastIndexOf(arr, target);

        if (index != -1) {
            System.out.println("Target is present"
                               + " at index "
                               + index);
        }
        else {
            System.out.println("Target is not present"
                               + " in the array");
        }
    }
}
```

**输出:**

```java
Target is not present in the array

```

**参考:**[https://Google . github . io/guava/releases/19.0/API/docs/com/Google/common/primitive/bytes . html # last indexof(byte[]，%20byte)](https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Bytes.html#lastIndexOf(byte[], %20byte))