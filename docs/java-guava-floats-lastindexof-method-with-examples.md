# Java 番石榴| Floats.lastIndexOf()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-floats-last indexof-method-with-examples/](https://www.geeksforgeeks.org/java-guava-floats-lastindexof-method-with-examples/)

番石榴库中 **[Floats 类](https://www.geeksforgeeks.org/floats-class-guava-java/)** 的 **lastIndexOf()** 方法用于查找浮点数组中给定浮点值的最后一个索引。要搜索的浮点值和要搜索的浮点数组都作为参数传递给此方法。它返回一个整数值，这是指定浮点值的最后一个索引。如果找不到该值，它将返回-1。

**语法:**

```
public static int lastIndexOf(float[] array,
                              float target)

```

**参数:**该方法接受两个强制参数:

*   **Array:** is an array of floating-point values to search for.
*   **Target:** is the floating point value of the last index to be searched in the floating point group.

**返回值:**该方法返回一个整数值，该整数值是指定浮点值的最后一个索引。如果找不到该值，它将返回-1。

下面的程序说明了这种方法:

**例 1:**

```
// Java code to show implementation of
// Guava's Floats.lastIndexOf() method

import com.google.common.primitives.Floats;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a float array
        float[] arr = { 1.2f, 2.2f, 3.2f, 4.2f,
                        3.2f, 5.6f, 3.2f, 4.4f };

        float target = 3.2f;

        // Using Floats.lastIndexOf() method
        // to get the index of last appearance
        // of a given element in array
        // and return -1 if element is
        // not found in the array
        int index
            = Floats.lastIndexOf(arr, target);

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

```
Target is present at index 6

```

**例 2:**

```
// Java code to show implementation of
// Guava's Floats.lastIndexOf() method

import com.google.common.primitives.Floats;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating a float array
        float[] arr = { 1.2f, 2.2f, 3.2f, 4.2f,
                        3.2f, 5.6f, 3.2f, 4.4f };

        float target = 10.2f;

        // Using Floats.lastIndexOf() method
        // to get the index of last appearance
        // of a given element in array
        // and return -1 if element is
        // not found in the array
        int index
            = Floats.lastIndexOf(arr, target);

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

```
Target is not present in the array

```

**参考:**[https://Google . github . io/guava/releases/19.0/API/docs/com/Google/common/primitive/floats . html # last indexof(float[]，%20float)](https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Floats.html#lastIndexOf(float[], %20float))