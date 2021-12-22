# Java 番石榴| Floats.indexOf(float[]数组，float[]目标)方法示例

> 原文:[https://www . geesforgeks . org/Java-guava-floats-index offoat-array-float-target-method-with-examples/](https://www.geeksforgeeks.org/java-guava-floats-indexoffloat-array-float-target-method-with-examples/)

**flowers . indexof(float[]数组，float[] target)** 法番石榴的[flowers 类](https://www.geeksforgeeks.org/floats-class-guava-java/)接受两个参数 ***数组*** 和 ***target*** 。如果目标存在于数组中，该方法返回其第一次出现的**的开始位置。如果数组中不存在目标，则该方法返回 **-1** 。**

****语法:****

> ****公共静态 int indexOf(float[]数组，float[] target)****

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
// Guava's Floats.indexOf(float[] array,
// float[] target) method

import com.google.common.primitives.Floats;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating an float array
        float[] arr = { 1.2f, 2.3f, 3.4f,
                        4.5f, 3.4f, 5.6f };

        float[] target = { 3.4f, 4.5f, 3.4f };

        System.out.println("Array: "
                           + Arrays.toString(arr));

        System.out.println("Target Array: "
                           + Arrays.toString(target));

        // Using Floats.indexOf(float[] array, float[] target)
        // method to get the start position of the first
        // occurrence of the specified target within array,
        // or -1 if there is no such occurrence.
        int index = Floats.indexOf(arr, target);

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
Array: [1.2, 2.3, 3.4, 4.5, 3.4, 5.6]
Target Array: [3.4, 4.5, 3.4]
Target is present at index 2

```

**例 2:**

```
// Java code to show implementation of
// Guava's Floats.indexOf(float[] array,
// float[] target) method

import com.google.common.primitives.Floats;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating an float array
        float[] arr = { 3.2f, 5.3f, 7.4f,
                        11.4f, 13.5f };

        float[] target = { 17.5f, 12.4f };

        System.out.println("Array: "
                           + Arrays.toString(arr));

        System.out.println("Target Array: "
                           + Arrays.toString(target));

        // Using Floats.indexOf(float[] array, float[] target)
        // method to get the start position of the first
        // occurrence of the specified target within array,
        // or -1 if there is no such occurrence.
        int index = Floats.indexOf(arr, target);

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
Array: [3.2, 5.3, 7.4, 11.4, 13.5]
Target Array: [17.5, 12.4]
Target is not present in the array

```

**参考:**[https://Google . github . io/guava/releases/22.0/API/docs/com/Google/common/primitive/floats . html # indexOf-float:A-float:A-](https://google.github.io/guava/releases/22.0/api/docs/com/google/common/primitives/Floats.html#indexOf-float:A-float:A-)**