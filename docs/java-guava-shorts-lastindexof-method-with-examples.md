# 爪哇番石榴|短裤. lastIndexOf()方法示例

> 原文:[https://www . geesforgeks . org/Java-guava-shots-last indexof-method-with-examples/](https://www.geeksforgeeks.org/java-guava-shorts-lastindexof-method-with-examples/)

番石榴库中 **[短裤类](https://www.geeksforgeeks.org/shorts-class-guava-java/)** 的 **lastIndexOf()** 方法用于查找短数组中给定短值的最后一个索引。要搜索的短值和要搜索的短数组都作为参数传递给此方法。它返回一个整数值，该整数值是指定短数值的最后一个索引。如果找不到该值，它将返回-1。

**语法:**

```java
public static int lastIndexOf(short[] array,
                              short target)

```

**参数:**该方法接受两个强制参数:

*   **Array:** is a short value array for which short values are to be searched.
*   **Target:** is the short value of the last index to be searched in the short array.

**返回值:**该方法返回一个整数值，该整数值是指定短数值的最后一个索引。如果找不到该值，它将返回-1。

下面的程序说明了这种方法:

**例 1:**

```java
// Java code to show implementation of
// Guava's Shorts.lastIndexOf() method

import com.google.common.primitives.Shorts;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a short array
        short[] arr = { 1, 2, 3, 4, 3, 5, 3, 4 };

        short target = 3;

        // Using Shorts.lastIndexOf() method
        // to get the index of last appearance
        // of a given element in array
        // and return -1 if element is
        // not found in the array
        int index
            = Shorts.lastIndexOf(arr, target);

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
// Guava's Shorts.lastIndexOf() method

import com.google.common.primitives.Shorts;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating a short array
        short[] arr = { 3, 5, 7, 11, 13 };

        short target = 17;

        // Using Shorts.lastIndexOf() method
        // to get the index of last appearance
        // of a given element in array
        // and return -1 if element is
        // not found in the array
        int index
            = Shorts.lastIndexOf(arr, target);

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

**参考:**[https://Google . github . io/guava/releases/23.0/API/docs/com/Google/common/primitives/短裤. html # last indexof-short:A-short-](https://google.github.io/guava/releases/23.0/api/docs/com/google/common/primitives/Shorts.html#lastIndexOf-short:A-short-)