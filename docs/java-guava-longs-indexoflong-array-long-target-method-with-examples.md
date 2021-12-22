# Java 番石榴| Longs.indexOf(long[]数组，long[]目标)方法示例

> 原文:[https://www . geesforgeks . org/Java-guava-longs-indexoflong-array-long-target-method-with-examples/](https://www.geeksforgeeks.org/java-guava-longs-indexoflong-array-long-target-method-with-examples/)

**Longs.indexOf(long【】阵，long【】目标)**法番石榴的 [Longs 类](https://www.geeksforgeeks.org/longs-class-guava-java/)接受两个参数 ***阵*** 和 ***目标*** 。如果目标存在于数组中，该方法返回其第一次出现的**的开始位置。如果数组中不存在目标，则该方法返回 **-1** 。**

****语法:****

> ****公共静态 int indexOf(long[]数组，long[]目标)****

****参数:**该方法接受两个参数:**

*   ****数组:**是检查目标数组索引的整数数组。**
*   ****目标:**作为指定数组的子序列进行搜索的数组。**

****返回值:**该方法返回如下整数值:**

***   If there is a target array in the array, return the **starting position where the target first appears *.****   Otherwise, if there is no target in the array, return **-1** .**

****异常:**该方法不抛出任何异常。**

**下面的例子说明了上述方法的实现:**

****例 1:****

```
// Java code to show implementation of
// Guava's Longs.indexOf(long[] array,
// long[] target) method

import com.google.common.primitives.Longs;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating an long array
        long[] arr = { 1, 2, 3, 4, 3, 5 };

        long[] target = { 3, 4, 3 };

        System.out.println("Array: "
                           + Arrays.toString(arr));

        System.out.println("Target Array: "
                           + Arrays.toString(target));

        // Using Longs.indexOf(long[] array, long[] target)
        // method to get the start position of the first
        // occurrence of the specified target within array,
        // or -1 if there is no such occurrence.
        int index = Longs.indexOf(arr, target);

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
Target Array: [3, 4, 3]
Target is present at index 2

```

**例 2:**

```
// Java code to show implementation of
// Guava's Longs.indexOf(long[] array,
// long[] target) method

import com.google.common.primitives.Longs;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating an long array
        long[] arr = { 3, 5, 7, 11, 13 };

        long[] target = { 23, 37 };

        System.out.println("Array: "
                           + Arrays.toString(arr));

        System.out.println("Target Array: "
                           + Arrays.toString(target));

        // Using Longs.indexOf(long[] array, long[] target)
        // method to get the start position of the first
        // occurrence of the specified target within array,
        // or -1 if there is no such occurrence.
        int index = Longs.indexOf(arr, target);

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
Target Array: [23, 37]
Target is not present in the array

```

**参考:**[https://Google . github . io/guava/releases/21.0/API/docs/com/Google/common/primitive/longs . html # indexOf-long:A-long:A-](https://google.github.io/guava/releases/21.0/api/docs/com/google/common/primitives/Longs.html#indexOf-long:A-long:A-)**