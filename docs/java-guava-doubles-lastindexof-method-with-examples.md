# 爪哇番石榴| Doubles.lastIndexOf()方法示例

> 原文:[https://www . geesforgeks . org/Java-guava-double-last indexof-method-with-examples/](https://www.geeksforgeeks.org/java-guava-doubles-lastindexof-method-with-examples/)

番石榴库中 **[双打类](https://www.geeksforgeeks.org/doubles-class-guava-java/)** 的 **lastIndexOf()** 方法用于查找双数组中给定双数值的最后一个索引。要搜索的双精度值和要搜索的双精度数组都作为参数传递给此方法。它返回一个整数值，这是指定双精度值的最后一个索引。如果找不到该值，它将返回-1。

**语法:**

```
public static int lastIndexOf(double[] array,
                              double target)

```

**参数:**该方法接受两个强制参数:

*   **Array:** is a binary array to search for binary values.
*   **Target:** is the double value to be searched by the last index in the double array.

**返回值:**该方法返回一个整数值，该整数值是指定双精度值的最后一个索引。如果找不到该值，它将返回-1。

下面的程序说明了这种方法:

**例 1:**

```
// Java code to show implementation of
// Guava's Doubles.lastIndexOf() method

import com.google.common.primitives.Doubles;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a double array
        double[] arr = { 1.2, 2.2, 3.2, 4.2,
                         3.2, 5.6, 3.2, 4.4 };

        double target = 3.2;

        // Using Doubles.lastIndexOf() method
        // to get the index of last appearance
        // of a given element in array
        // and return -1 if element is
        // not found in the array
        int index
            = Doubles.lastIndexOf(arr, target);

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
// Guava's Doubles.lastIndexOf() method

import com.google.common.primitives.Doubles;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating a double array
        double[] arr = { 1.2, 2.2, 3.2, 4.2,
                         3.2, 5.6, 3.2, 4.4 };

        double target = 10.2;

        // Using Doubles.lastIndexOf() method
        // to get the index of last appearance
        // of a given element in array
        // and return -1 if element is
        // not found in the array
        int index
            = Doubles.lastIndexOf(arr, target);

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

**参考:**[https://Google . github . io/guava/releases/19.0/API/docs/com/Google/common/primitive/double . html # last indexof(double[]，%20double)](https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Doubles.html#lastIndexOf(double[], %20double))