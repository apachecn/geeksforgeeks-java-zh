# Java 番石榴| Chars.indexOf(char[]数组，char 目标)方法，示例

> 原文:[https://www . geesforgeks . org/Java-guava-chars-indexofchar-array-char-target-method-with-examples-2/](https://www.geeksforgeeks.org/java-guava-chars-indexofchar-array-char-target-method-with-examples-2/)

**Chars.indexOf(char[]数组，char target)** 法番石榴的 [Chars 类](https://www.geeksforgeeks.org/chars-class-guava-java/)接受两个参数 ***数组*** 和 ***target*** 。如果目标存在于数组中，该方法返回其第一次出现的**的位置。如果数组中不存在目标，则该方法返回 **-1** 。**

****语法:****

> ****公共静态 int indexOf(char[]数组，char target)****

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
// Guava's Chars.indexOf(char[] array,
// char target) method

import com.google.common.primitives.Chars;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating an char array
        char[] arr = { 'G', 'F', 'G', 'E', 'E' };

        char target = 'E';

        System.out.println("Array: "
                           + Arrays.toString(arr));

        System.out.println("Target: " + target);

        // Using Chars.indexOf(char[] array, char target)
        // method to get the position of the first
        // occurrence of the specified target within array,
        // or -1 if there is no such occurrence.
        int index = Chars.indexOf(arr, target);

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
Array: [G, F, G, E, E]
Target: E
Target is present at index 3

```

**例 2:**

```
// Java code to show implementation of
// Guava's Chars.indexOf(char[] array,
// char target) method

import com.google.common.primitives.Chars;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating an char array
        char[] arr = { 'H', 'E', 'L', 'L', 'O' };

        char target = 'G';

        System.out.println("Array: "
                           + Arrays.toString(arr));

        System.out.println("Target: " + target);

        // Using Chars.indexOf(char[] array, char target)
        // method to get the start position of the first
        // occurrence of the specified target within array,
        // or -1 if there is no such occurrence.
        int index = Chars.indexOf(arr, target);

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
Array: [H, E, L, L, O]
Target: G
Target is not present in the array

```

**参考:**[https://Google . github . io/guava/releases/18.0/API/docs/com/Google/common/primitive/chars . html # indexOf(char[]，%20char)](https://google.github.io/guava/releases/18.0/api/docs/com/google/common/primitives/Chars.html#indexOf(char[], %20char))**