# Java 番石榴| Doubles.indexOf(double[]数组，双目标)方法示例

> 原文:[https://www . geesforgeks . org/Java-guava-double-indexofdouble-array-double-target-method-with-examples-2/](https://www.geeksforgeeks.org/java-guava-doubles-indexofdouble-array-double-target-method-with-examples-2/)

**双打指数番石榴[双打类](https://www.geeksforgeeks.org/doubles-class-guava-java/)的**法接受两个参数 ***阵*** 和 ***目标*** 。如果目标存在于数组中，该方法返回其第一次出现的**的位置。如果数组中不存在目标，则该方法返回 **-1** 。**

****语法:****

> ****公共静态 int indexOf(double[]数组，double target)****

****参数:**该方法接受两个参数:**

*   ****数组:**是检查目标数组索引的整数数组。**
*   ****目标:**是在指定数组中作为元素搜索的值。**

****返回值:**该方法返回一个整数值如下:**

***   If the target exists in the array, the **position where the target first appears *is returned.****   Otherwise, if there is no target in the array, return **-1** .**

****异常:**该方法不抛出任何异常。**

**下面的例子说明了上述方法的实现:**

****例 1:****

```java
// Java code to show implementation of
// Guava's Doubles.indexOf(double[] array,
// double target) method

import com.google.common.primitives.Doubles;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating an double array
        double[] arr = { 3.2, 5.3, 7.4, 11.4, 13.5 };

        double target = 7.4;

        System.out.println("Array: "
                           + Arrays.toString(arr));

        System.out.println("Target: " + target);

        // Using Doubles.indexOf(double[] array, double target)
        // method to get the position of the first
        // occurrence of the specified target within array,
        // or -1 if there is no such occurrence.
        int index = Doubles.indexOf(arr, target);

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

****输出:**

```java
Array: [3.2, 5.3, 7.4, 11.4, 13.5]
Target: 7.4
Target is present at index 2

```

**例 2:**

```java
// Java code to show implementation of
// Guava's Doubles.indexOf(double[] array,
// double target) method

import com.google.common.primitives.Doubles;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating an double array
        double[] arr = { 3, 5, 7, 11, 13 };

        double target = 23;

        System.out.println("Array: "
                           + Arrays.toString(arr));

        System.out.println("Target: " + target);

        // Using Doubles.indexOf(double[] array, double target)
        // method to get the start position of the first
        // occurrence of the specified target within array,
        // or -1 if there is no such occurrence.
        int index = Doubles.indexOf(arr, target);

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
Array: [3.0, 5.0, 7.0, 11.0, 13.0]
Target: 23.0
Target is not present in the array

```

**参考:**[https://Google . github . io/guava/releases/19.0/API/docs/com/Google/common/primitive/double . html # indexOf(double[]，%20double)](https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Doubles.html#indexOf(double[], %20double))**