# Java Guava | Booleans.indexOf(布尔[]数组，布尔[]目标)方法，示例

> 原文:[https://www . geesforgeks . org/Java-guava-booleans-indexofboolean-array-boolean-target-method-with-examples/](https://www.geeksforgeeks.org/java-guava-booleans-indexofboolean-array-boolean-target-method-with-examples/)

**Booleans.indexOf(布尔[]数组，布尔[]目标)**法番石榴的 [Booleans 类](https://www.geeksforgeeks.org/booleans-class-guava-java/)接受两个参数 ***数组*** 和 ***目标*** 。如果目标存在于数组中，该方法返回其第一次出现的**的开始位置。如果数组中不存在目标，则该方法返回 **-1** 。**

****语法:****

```
public static int indexOf(boolean[] array,
                          boolean[] target) 
```

****参数:**该方法接受两个参数:**

***   **Array:** An array searches for the sequence target.*   **Target:** The array to be searched as a subsequence of the array.**

****返回值:**该方法返回:**

*   **目标第一次出现*的起始位置*，如果目标存在于数组中。**
*   **-1 如果目标不在阵列中。**

****异常:**该方法不抛出任何异常。**

**下面的例子说明了上述方法的实现:**

****例 1:****

```
// Java code to show implementation of
// Guava's Booleans.indexOf(boolean[] array,
// boolean[] target) method

import com.google.common.primitives.Booleans;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a boolean array
        boolean[] arr = { false, true, false,
                          false, true };

        boolean[] target = { false, false };

        // Using indexOf(boolean[] array, boolean[] target)
        // method to get the start position of the first
        // occurrence of the specified target within array,
        // or -1 if there is no such occurrence.
        int index = Booleans.indexOf(arr, target);

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

****例 2 :****

```
// Java code to show implementation of
// Guava's Booleans.indexOf(boolean[] array,
// boolean[] target) method

import com.google.common.primitives.Booleans;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a boolean array
        boolean[] arr = { false, true, false,
                          false, true };

        boolean[] target = { false, false, false };

        // Using indexOf(boolean[] array, boolean[] target)
        // method to get the start position of the first
        // occurrence of the specified target within array,
        // or -1 if there is no such occurrence.
        int index = Booleans.indexOf(arr, target);

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

****参考:**[https://Google . github . io/guava/releases/20.0/API/docs/com/Google/common/primitive/booleans . html # indexOf-boolean:A-boolean:A-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/primitives/Booleans.html#indexOf-boolean:A-boolean:A-)**