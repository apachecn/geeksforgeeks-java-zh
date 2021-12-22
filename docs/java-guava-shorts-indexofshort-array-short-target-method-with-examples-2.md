# Java 番石榴| Shorts.indexOf(短[]数组，短目标)方法，示例

> 原文:[https://www . geesforgeks . org/Java-guava-shots-indexofshort-array-short-target-method-with-examples-2/](https://www.geeksforgeeks.org/java-guava-shorts-indexofshort-array-short-target-method-with-examples-2/)

**短裤指数 Of(短[]阵，短目标)**法番石榴的[短裤类](https://www.geeksforgeeks.org/shorts-class-guava-java/)接受两个参数 ***阵*** 和 ***目标*** 。如果目标存在于数组中，该方法返回其第一次出现的**的位置。如果数组中不存在目标，则该方法返回 **-1** 。**

****语法:****

> ****公共静态 int indexOf(短[]数组，短目标)****

****参数:**该方法接受两个参数:**

*   ****数组:**是检查目标数组索引的整数数组。**
*   ****目标:**是在指定数组中作为元素搜索的值。**

****返回值:**该方法返回一个整数值如下:**

***   If the target exists in the array, the **position where the target first appears *is returned.****   Otherwise, if there is no target in the array, return **-1** .**

****异常:**该方法不抛出任何异常。**

**下面的例子说明了上述方法的实现:**

****例 1:****

```
// Java code to show implementation of
// Guava's Shorts.indexOf(short[] array,
// short target) method

import com.google.common.primitives.Shorts;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating an short array
        short[] arr = { 1, 2, 3, 4, 3, 5 };

        short target = 3;

        System.out.println("Array: "
                           + Arrays.toString(arr));

        System.out.println("Target: " + target);

        // Using Shorts.indexOf(short[] array, short target)
        // method to get the position of the first
        // occurrence of the specified target within array,
        // or -1 if there is no such occurrence.
        int index = Shorts.indexOf(arr, target);

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

```
Array: [1, 2, 3, 4, 3, 5]
Target: 3
Target is present at index 2

```

**例 2:**

```
// Java code to show implementation of
// Guava's Shorts.indexOf(short[] array,
// short target) method

import com.google.common.primitives.Shorts;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating an short array
        short[] arr = { 3, 5, 7, 11, 13 };

        short target = 23;

        System.out.println("Array: "
                           + Arrays.toString(arr));

        System.out.println("Target: " + target);

        // Using Shorts.indexOf(short[] array, short target)
        // method to get the start position of the first
        // occurrence of the specified target within array,
        // or -1 if there is no such occurrence.
        int index = Shorts.indexOf(arr, target);

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

```
Array: [3, 5, 7, 11, 13]
Target: 23
Target is not present in the array

```

**参考:**[https://Google . github . io/guava/releases/23.0/API/docs/com/Google/common/primitives/短裤. html#indexOf-short:A-short-](https://google.github.io/guava/releases/23.0/api/docs/com/google/common/primitives/Shorts.html#indexOf-short:A-short-)**