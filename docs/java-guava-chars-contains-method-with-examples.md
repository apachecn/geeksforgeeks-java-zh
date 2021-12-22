# Java 番石榴| Chars.contains()方法示例

> 原文:[https://www . geesforgeks . org/Java-guava-chars-contains-method-with-examples/](https://www.geeksforgeeks.org/java-guava-chars-contains-method-with-examples/)

番石榴库中 **[Chars 类](https://www.geeksforgeeks.org/chars-class-guava-java/)** 的 **contains()** 方法用于检查指定的字符值数组中是否存在指定的值。要搜索的字符值和要搜索的字符数组都作为参数。

**语法:**

```
public static boolean contains(char[] array, 
                               char target)

```

**参数:**该方法接受两个强制参数:

*   **Array:** is an array of character values in which the target value is searched.
*   **Target:** is the character value in the array to be searched for.

**返回值:**该方法返回一个布尔值，说明目标字符值是否存在于指定的字符数组中。如果数组中存在目标值，则返回*真*。否则返回*假*。

下面的程序说明了 contains()方法的使用:

**例 1:**

```
// Java code to show implementation of
// Guava's Chars.contains() method

import com.google.common.primitives.Chars;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a character array
        char[] arr = { 'g', 'e', 'e', 'k', 's' };

        char target = 'k';

        // Using Chars.contains() method to search
        // for an element in the array. The method
        // returns true if element is found, else
        // returns false
        if (Chars.contains(arr, target))
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
// Guava's Chars.contains() method

import com.google.common.primitives.Chars;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a character array
        char[] arr = { 'g', 'e', 'e', 'k', 's' };

        char target = 'a';

        // Using Chars.contains() method to search
        // for an element in the array. The method
        // returns true if element is found, else
        // returns false
        if (Chars.contains(arr, target))
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

**参考:**[https://Google . github . io/guava/releases/18.0/API/docs/com/Google/common/primitive/chars . html #包含(char[]，%20char)](https://google.github.io/guava/releases/18.0/api/docs/com/google/common/primitives/Chars.html#contains(char[], %20char))