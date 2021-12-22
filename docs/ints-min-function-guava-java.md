# Ints min()函数|番石榴| Java

> 原文:[https://www.geeksforgeeks.org/ints-min-function-guava-java/](https://www.geeksforgeeks.org/ints-min-function-guava-java/)

番石榴的**T1Ints。min()** 返回数组中最少的*值。*

***语法:***

```
*public static int min(int... array)* 
```

***参数:**该方法以 ***数组*** 为参数，该参数为 *int* 值的非空数组。*

***返回值:**该方法返回数组中存在的小于或等于数组中其他值的值*。**

****异常:**阵为空则法掷***IllegalArgumentException***。**

**以下示例说明了 Ints.min()方法:**

****例 1:****

```
**// Java code to show implementation of
// Guava's Ints.min() method

import com.google.common.primitives.Ints;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating an integer array
        int[] arr = { 2, 4, 6, 10, 0, -5, 15 };

        // Using Ints.min() method to get the
        // minimum value present in the array
        System.out.println("Minimum Value is: "
                           + Ints.min(arr));
    }
}**
```

****输出:**

```
Minimum Value is: -5

```

**示例 2:** 演示 IllegalArgumentException

```
// Java code to show implementation of
// Guava's Ints.min() method

import com.google.common.primitives.Ints;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        try {
            // Creating an integer array
            int[] arr = {};

            // Using Ints.min() method to get the
            // minimum value present in the array
            // This should raise "IllegalArgumentException"
            // as the array is empty
            System.out.println("Minimum Value is : "
                               + Ints.min(arr));
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```
Exception: java.lang.IllegalArgumentException

```

**参考:**[https://Google . github . io/guava/releases/22.0/API/docs/com/Google/common/primitives/ints . html # min-int……-](https://google.github.io/guava/releases/22.0/api/docs/com/google/common/primitives/Ints.html#min-int...-)**