# Java 番石榴| Booleans.lastIndexOf()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-booleans-last indexof-method-with-examples/](https://www.geeksforgeeks.org/java-guava-booleans-lastindexof-method-with-examples/)

番石榴库中 **[布尔类](https://www.geeksforgeeks.org/booleans-class-guava-java/)** 的 **lastIndexOf()** 方法用于查找布尔数组中给定布尔值的最后一个索引。要搜索的布尔值和要搜索的布尔数组都作为参数传递给此方法。它返回一个整数值，这是指定布尔值的最后一个索引。如果找不到该值，它将返回-1。

**语法:**

```
public static int lastIndexOf(boolean[] array,
                              boolean target)

```

**参数:**该方法接受两个强制参数:

*   **Array:** is an array of Boolean values to search for.
*   **Target:** is the Boolean value to be searched by the last index in the Boolean array.

**返回值:**该方法返回一个整数值，该整数值是指定布尔值的最后一个索引。如果找不到该值，它将返回-1。

下面的程序说明了这种方法:

**示例-1:**

```
// Java code to show implementation of
// Guava's Booleans.lastIndexOf() method

import com.google.common.primitives.Booleans;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating a boolean array
        boolean[] arr = { true, false, false,
                          true, true };

        boolean target = true;

        // Using Booleans.lastIndexOf() method
        // to get the index of last appearance
        // of a given element in array
        // and return -1 if element
        // is not found in the array
        int index = Booleans.lastIndexOf(arr, target);

        if (index != -1) {
            System.out.println("Target is present at index "
                               + index);
        }
        else {
            System.out.println("Target is not present "
                               + "in the array");
        }
    }
}
```

**输出:**

```
Target is present at index 4

```

**示例-2:**

```
// Java code to show implementation of
// Guava's Booleans.lastIndexOf() method

import com.google.common.primitives.Booleans;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating a boolean array
        boolean[] arr = { true, true, true,
                          true, true };

        boolean target = false;

        // Using Booleans.lastIndexOf() method to get the
        // index of last appearance of a given element
        // in array and return -1 if element is
        // not found in the array
        int index = Booleans.lastIndexOf(arr, target);

        if (index != -1) {
            System.out.println("Target is present at index "
                               + index);
        }
        else {
            System.out.println("Target is not present "
                               + "in the array");
        }
    }
}
```

**输出:**

```
Target is not present in the array

```

**参考:**[https://Google . github . io/guava/releases/20.0/API/docs/com/Google/common/primitive/booleans . html # last indexof-boolean:A-boolean-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/primitives/Booleans.html#lastIndexOf-boolean:A-boolean-)