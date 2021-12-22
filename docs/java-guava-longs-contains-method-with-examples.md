# Java 番石榴| Longs.contains()方法示例

> 原文:[https://www . geesforgeks . org/Java-guava-longs-contains-method-with-examples/](https://www.geeksforgeeks.org/java-guava-longs-contains-method-with-examples/)

番石榴的[朗斯等级](https://www.geeksforgeeks.org/longs-class-guava-java/)的**朗斯包含()**方法用于检查数组中是否存在值，即目标。该目标值和数组被作为该方法的参数。此方法返回一个布尔值，该值表示目标值是否为

**语法:**

```
public static boolean contains(long[] array, 
                               long target)

```

**参数:**该方法接受两个参数:

*   **array:** is the value array for which the target value is to be searched.
*   **Target:** is the long value to be checked for existence.

**返回值:**该方法返回 ***真*** 如果对于 I 的某个值，i <sub>th</sub> 索引处存在的值等于目标，否则返回 ***假*** 。

**异常:**方法不抛出任何异常。

**例 1:**

```
// Java code to show implementation of
// Guava's Longs.contains() method

import com.google.common.primitives.Longs;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating a long array
        long[] arr = { 5L, 4L, 3L, 2L, 1L };

        long target = 3L;

        // Using Longs.contains() method to search
        // for an element in the array. The method
        // returns true if element is found, else
        // returns false
        if (Longs.contains(arr, target))
            System.out.println("Target is present"
                               + " in the array");
        else
            System.out.println("Target is not "
                               + "present in the array");
    }
}
```

**输出:**

```
Target is present in the array

```

**例 2:**

```
// Java code to show implementation of
// Guava's Longs.contains() method

import com.google.common.primitives.Longs;
import java.util.Arrays;

class GFG {
    // Driver's code
    public static void main(String[] args)
    {
        // Creating a long array
        long[] arr = { 2L, 4L, 6L, 8L, 10L };

        long target = 7L;

        // Using Longs.contains() method to search
        // for an element in the array. The method
        // returns true if element is found, else
        // returns false
        if (Longs.contains(arr, target))
            System.out.println("Target is present"
                               + " in the array");
        else
            System.out.println("Target is not "
                               + "present in the array");
    }
}
```

**输出:**

```
Target is not present in the array

```

**参考:**[https://Google . github . io/guava/releases/21.0/API/docs/com/Google/common/primitives/longs . html # contains-long:A-long-](https://google.github.io/guava/releases/21.0/api/docs/com/google/common/primitives/Longs.html#contains-long:A-long-)