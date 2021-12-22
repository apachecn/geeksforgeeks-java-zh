# Java 番石榴| Bytes.contains()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-bytes-contains-method-with-examples/](https://www.geeksforgeeks.org/java-guava-bytes-contains-method-with-examples/)

**字节. contains()** 法番石榴的[字节类](https://www.geeksforgeeks.org/bytes-class-guava-java/)接受两个参数 ***阵*** 和 ***目标*** 。方法用于检查数组中是否存在目标元素。

**语法:**

```java
public static boolean contains(byte[] array,
                               byte target)

```

**参数:**该方法接受两个参数:

*   **Array:** An array of byte values, which may be empty.
*   **Target:** To check whether the original byte value exists in the array.

**返回值:**如果目标作为元素出现在数组中的任何位置，则该方法返回 ***true*** ，如果目标不出现在数组中的任何位置，则返回 ***false*** 。

**异常:**该方法不抛出任何异常。

下面的例子说明了上述方法的实现:

**例 1:**

```java
// Java code to show implementation of
// Guava's Bytes.contains() method

import com.google.common.primitives.Bytes;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a Byte array
        byte[] arr = { 5, 4, 3, 2, 1 };

        byte target = 3;

        // Using Bytes.contains() method to search
        // for an element in the array. The method
        // returns true if element is found, else
        // returns false
        if (Bytes.contains(arr, target))
            System.out.println("Target is present"
                               + " in the array");
        else
            System.out.println("Target is not present"
                               + " in the array");
    }
}
```

**输出:**

```java
Target is present in the array

```

**例 2 :**

```java
// Java code to show implementation of
// Guava's Bytes.contains() method

import com.google.common.primitives.Bytes;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating a Byte array
        byte[] arr = { 2, 4, 6, 8, 10 };

        byte target = 7;

        // Using Bytes.contains() method to search
        // for an element in the array. The method
        // returns true if element is found, else
        // returns false
        if (Bytes.contains(arr, target))
            System.out.println("Target is present"
                               + " in the array");
        else
            System.out.println("Target is not present"
                               + " in the array");
    }
}
```

**输出:**

```java
Target is not present in the array

```

**参考:**[https://Google . github . io/guava/releases/19.0/API/docs/com/Google/common/primitive/bytes . html #包含(byte[]，%20byte)](https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Bytes.html#contains(byte[], %20byte))