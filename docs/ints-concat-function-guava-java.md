# Ints concat()函数|番石榴| Java

> 原文:[https://www . geesforgeks . org/ints-concat-function-guava-Java/](https://www.geeksforgeeks.org/ints-concat-function-guava-java/)

番石榴的**T1Ints。concat()** 方法用于将作为参数传递的数组组合成单个数组。此方法返回组合成单个数组的每个数组中的值。例如，concat(new int[] {a，b}、new int[] {}、new int[] {c}返回数组{a，b，c}。

**语法:**

```java
public static int[] concat(int[]... arrays)
```

**参数:**该方法以 ***数组*** 为参数，表示零个或多个 int 数组。

**返回值:**这个方法按顺序返回一个包含所有来自源数组的值的数组。

**例 1:**

```java
// Java code to show implementation of
// Guava's Ints.concat() method

import com.google.common.primitives.Ints;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating 2 Integer arrays
        int[] arr1 = { 1, 2, 3, 4, 5 };
        int[] arr2 = { 6, 2, 7, 0, 8 };

        // Using Ints.concat() method to combine
        // elements from both arrays into a single array
        int[] res = Ints.concat(arr1, arr2);

        // Displaying the single combined array
        System.out.println("Combined Array: "
                           + Arrays.toString(res));
    }
}
```

**输出:**

```java
Combined Array: [1, 2, 3, 4, 5, 6, 2, 7, 0, 8]

```

**例 2:**

```java
// Java code to show implementation of
// Guava's Ints.concat() method

import com.google.common.primitives.Ints;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating 4 Integer arrays
        int[] arr1 = { 1, 2, 3 };
        int[] arr2 = { 4, 5 };
        int[] arr3 = { 6, 7, 8 };
        int[] arr4 = { 9, 0 };

        // Using Ints.concat() method to combine
        // elements from both arrays into a single array
        int[] res = Ints.concat(arr1, arr2, arr3, arr4);

        // Displaying the single combined array
        System.out.println("Combined Array: "
                           + Arrays.toString(res));
    }
}
```

**输出:**

```java
Combined Array: [1, 2, 3, 4, 5, 6, 7, 8, 9, 0]

```

**参考:**[https://Google . github . io/guava/releases/22.0/API/docs/com/Google/common/primitives/ints . html # concat-int:A……-](https://google.github.io/guava/releases/22.0/api/docs/com/google/common/primitives/Ints.html#concat-int:A...-)