# Ints indexOf()函数|番石榴| Java

> 原文:[https://www . geesforgeks . org/ints-indexof-function-guava-Java/](https://www.geeksforgeeks.org/ints-indexof-function-guava-java/)

番石榴的**T1Ints。indexOf(int[]数组，int target)** 方法返回数组中值目标的第一个 ***外观的索引。***

**语法:**

```java
public static int indexOf(int[] array, int target)

```

**参数:**此方法接受以下参数:

*   **Array:** An array of int values, which may be empty.
*   **Target:** An original int value.

**返回值:**此方法返回 ***最小索引*** i 为哪个数组[i] ==目标，或者 ***-1*** 如果不存在这样的索引。

**例 1:**

```java
// Java code to show implementation of
// Guava's Ints.indexOf() method

import com.google.common.primitives.Ints;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating an integer array
        int[] arr = { 1, 2, 3, 4, 3, 5 };

        int target = 3;

        // Using Ints.indexOf(int[] array, int target)
        // method to get the index of first appearance
        // of a given element in array and return -1
        // if element is not found in the array
        int index = Ints.indexOf(arr, target);

        if (index != -1) {
            System.out.println("Target is present at index "
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
Target is present at index 2

```

**例 2:**

```java
// Java code to show implementation of
// Guava's Ints.indexOf() method

import com.google.common.primitives.Ints;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating an integer array
        int[] arr = { 3, 5, 7, 11, 13 };

        int target = 17;

        // Using Ints.indexOf(int[] array, int target) method
        // to get the index of first appearance of a
        // given element in array and return -1 if
        // element is not found in the array
        int index = Ints.indexOf(arr, target);

        if (index != -1) {
            System.out.println("Target is present at index "
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

**参考:**[https://Google . github . io/guava/releases/22.0/API/docs/com/Google/common/primitives/ints . html # indexOf-int:A-int-](https://google.github.io/guava/releases/22.0/api/docs/com/google/common/primitives/Ints.html#indexOf-int:A-int-)