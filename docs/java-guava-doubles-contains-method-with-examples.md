# Java 番石榴| Doubles.contains()方法示例

> 原文:[https://www . geesforgeks . org/Java-guava-double-contains-method-with-examples/](https://www.geeksforgeeks.org/java-guava-doubles-contains-method-with-examples/)

番石榴库中 **[双打类](https://www.geeksforgeeks.org/doubles-class-guava-java/)** 的**包含()**方法用于检查指定的双数值数组中是否存在指定的数值。要搜索的双精度值和要搜索的双精度数组都作为参数。

**语法:**

```java
public static boolean contains(double[] array,
                               double target)

```

**参数:**该方法接受两个强制参数:

*   **数组:**是要搜索目标值的双值数组。
*   **目标:**是要在数组中搜索存在的双精度值。

**返回值:**该方法返回一个布尔值，说明目标双精度值是否出现在指定的双精度数组中。如果数组中存在目标值，则返回*真*。否则返回*假*。

下面的程序说明了 contains()方法的使用:

**例 1:**

```java
// Java code to show implementation of
// Guava's Doubles.contains() method

import com.google.common.primitives.Doubles;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a Double array
        double[] arr = { 5.2, 4.2, 3.4, 2.3, 1.5 };

        double target = 3.4;

        // Using Doubles.contains() method to search
        // for an element in the array. The method
        // returns true if element is found, else
        // returns false
        if (Doubles.contains(arr, target))
            System.out.println("Target is present"
                               + " in the array");
        else
            System.out.println("Target is not present"
                               + " in the array");
    }
}
```

**Output:**

```java
Target is present in the array

```

**例 2:**

```java
// Java code to show implementation of
// Guava's Doubles.contains() method

import com.google.common.primitives.Doubles;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a Double array
        double[] arr = { 2.3, 4.4, 6.5, 8.6, 10.7 };

        double target = 7.5;

        // Using Doubles.contains() method to search
        // for an element in the array. The method
        // returns true if element is found, else
        // returns false
        if (Doubles.contains(arr, target))
            System.out.println("Target is present"
                               + " in the array");
        else
            System.out.println("Target is not present"
                               + " in the array");
    }
}
```

**Output:**

```java
Target is not present in the array

```

**参考:**
[https://Google . github . io/guava/releases/19.0/API/docs/com/Google/common/primitive/double . html #包含(double[]，%20double)](https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Doubles.html#contains(double[], %20double))