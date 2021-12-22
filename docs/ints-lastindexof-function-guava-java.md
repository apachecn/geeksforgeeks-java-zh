# Ints lastIndexOf()函数|番石榴| Java

> 原文:[https://www . geesforgeks . org/ints-last indexof-function-guava-Java/](https://www.geeksforgeeks.org/ints-lastindexof-function-guava-java/)

番石榴的**T1Ints。lastIndexOf()** 返回数组中值目标最后一次出现的*的索引。*

***语法:***

```java
*public static int 
  lastIndexOf(int[] array, int target)* 
```

***参数:***

**   **Array:** An array of int values, which may be empty.*   **Target:** An original int value.*

***返回值:**ints . indexof()方法返回 ***最大索引*** i 为哪个数组[i] ==目标，或者 ***-1*** 如果不存在这样的索引。*

***例 1:***

```java
*// Java code to show implementation of
// Guava's Ints.lastIndexOf() method

import com.google.common.primitives.Ints;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating an integer array
        int[] arr = { 1, 2, 3, 4, 3, 5, 3, 4 };

        int target = 3;

        // Using Ints.lastIndexOf() method to get the
        // index of last appearance of a given element
        // in array and return -1 if element is
        // not found in the array
        int index = Ints.lastIndexOf(arr, target);

        if (index != -1) {
            System.out.println("Target is present at index "
                               + index);
        }
        else {
            System.out.println("Target is not present"
                               + " in the array");
        }
    }
}*
```

***输出:**

```java
Target is present at index 6

```

**例 2 :**

```java
// Java code to show implementation of
// Guava's Ints.lastIndexOf() method

import com.google.common.primitives.Ints;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating an integer array
        int[] arr = { 3, 5, 7, 11, 13 };

        int target = 17;

        // Using Ints.lastIndexOf() method to get the
        // index of last appearance of a given element
        // in array and return -1 if element is
        // not found in the array
        int index = Ints.lastIndexOf(arr, target);

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

**参考:**[https://Google . github . io/guava/releases/22.0/API/docs/com/Google/common/primitives/ints . html # last indexof-int:A-int-](https://google.github.io/guava/releases/22.0/api/docs/com/google/common/primitives/Ints.html#lastIndexOf-int:A-int-)*