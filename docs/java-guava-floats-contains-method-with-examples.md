# Java 番石榴| Floats.contains()方法示例

> 原文:[https://www . geesforgeks . org/Java-guava-floats-contains-method-with-examples/](https://www.geeksforgeeks.org/java-guava-floats-contains-method-with-examples/)

番石榴库中 **[浮动类](https://www.geeksforgeeks.org/floats-class-guava-java/)** 的**包含()**方法用于检查指定的浮动值数组中是否存在指定的值。要搜索的浮点值和要搜索的浮点数组都作为参数。

**语法:**

```
public static boolean contains(float[] array,
                               float target)

```

**参数:**该方法接受两个强制参数:

*   **Array:** is an array of floating-point values in which the target value is searched.
*   **Target:** is the floating-point value in the array to be searched for.

**返回值:**该方法返回一个布尔值，说明目标浮点值是否出现在指定的浮点数组中。如果数组中存在目标值，则返回*真*。否则返回*假*。

下面的程序说明了 contains()方法的使用:

**例 1:**

```
// Java code to show implementation of
// Guava's Floats.contains() method

import com.google.common.primitives.Floats;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a Float array
        float[] arr = { 5.2f, 4.2f, 3.4f, 2.3f, 1.5f };

        float target = 3.4f;

        // Using Floats.contains() method to search
        // for an element in the array. The method
        // returns true if element is found, else
        // returns false
        if (Floats.contains(arr, target))
            System.out.println("Target is present"
                               + " in the array");
        else
            System.out.println("Target is not present"
                               + " in the array");
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
// Guava's Floats.contains() method

import com.google.common.primitives.Floats;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a Float array
        float[] arr = { 2.3f, 4.4f, 6.5f, 8.6f, 10.7f };

        float target = 7.5f;

        // Using Floats.contains() method to search
        // for an element in the array. The method
        // returns true if element is found, else
        // returns false
        if (Floats.contains(arr, target))
            System.out.println("Target is present"
                               + " in the array");
        else
            System.out.println("Target is not present"
                               + " in the array");
    }
}
```

**输出:**

```
Target is not present in the array

```

**参考:**[https://Google . github . io/guava/releases/19.0/API/docs/com/Google/common/primitive/floats . html #包含(float[]，%20float)](https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Floats.html#contains(float[], %20float))