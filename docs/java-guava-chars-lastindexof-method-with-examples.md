# Java 番石榴| Chars.lastIndexOf()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-chars-last indexof-method-with-examples/](https://www.geeksforgeeks.org/java-guava-chars-lastindexof-method-with-examples/)

番石榴库中 **[Chars 类](https://www.geeksforgeeks.org/chars-class-guava-java/)** 的 **lastIndexOf()** 方法用于查找给定字符值在字符数组中的最后一个索引。要搜索的字符值和要搜索的字符数组都作为参数传递给此方法。它返回一个整数值，这是指定字符值的最后一个索引。如果找不到该值，它将返回-1。

**语法:**

```java
public static int lastIndexOf(char[] array,
                              char target)

```

**参数:**该方法接受两个强制参数:

*   **Array:** is the array of character values to search for.
*   **Target:** is the character value to be searched by the last index in the character array.

**返回值:**该方法返回一个整数值，该整数值是指定字符值的最后一个索引。如果找不到该值，它将返回-1。

下面的程序说明了这种方法:

**例 1:**

```java
// Java code to show implementation of
// Guava's Chars.lastIndexOf() method

import com.google.common.primitives.Chars;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a char array
        char[] arr = { 'a', 'b', 'c', 'd',
                       'b', 'c', 'b', 'd' };

        char target = 'b';

        // Using Chars.lastIndexOf() method
        // to get the index of last appearance
        // of a given element in array
        // and return -1 if element is
        // not found in the array
        int index
            = Chars.lastIndexOf(arr, target);

        if (index != -1) {
            System.out.println("Target is present"
                               + " at index "
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
Target is present at index 6

```

**例 2:**

```java
// Java code to show implementation of
// Guava's Chars.lastIndexOf() method

import com.google.common.primitives.Chars;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating a char array
        char[] arr = { 'a', 'b', 'c', 'd',
                       'b', 'c', 'b', 'd' };

        char target = 'z';

        // Using Chars.lastIndexOf() method
        // to get the index of last appearance
        // of a given element in array
        // and return -1 if element is
        // not found in the array
        int index
            = Chars.lastIndexOf(arr, target);

        if (index != -1) {
            System.out.println("Target is present"
                               + " at index "
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
Target is not present in the array

```

**参考:**[https://Google . github . io/guava/releases/18.0/API/docs/com/Google/common/primitives/chars . html # lastindexof(char[]，%20char)](https://google.github.io/guava/releases/18.0/api/docs/com/google/common/primitives/Chars.html#lastIndexOf(char[], %20char))