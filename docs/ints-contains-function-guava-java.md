# Ints 包含()函数|番石榴| Java

> 原文:[https://www . geesforgeks . org/ints-contains-function-guava-Java/](https://www.geeksforgeeks.org/ints-contains-function-guava-java/)

番石榴的[**Ints**T3**。如果目标作为元素出现在数组中的任何位置，contains()** 返回 ***true*** 。
**语法:**](https://www.geeksforgeeks.org/ints-class-guava-java/) 

```java
public static boolean 
  contains(int[] array, int target)
```

**参数:**该方法接受以下参数:

*   **数组:**int 值的数组，可能为空。
*   **目标:**一个原始 int 值。

**返回值:**这个方法返回一个布尔值。如果数组[i] ==目标值为 i.
**则返回*真*示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to show implementation of
// Guava's Ints.contains() method

import com.google.common.primitives.Ints;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating an Integer array
        int[] arr = { 5, 4, 3, 2, 1 };

        int target = 3;

        // Using Ints.contains() method to search
        // for an element in the array. The method
        // returns true if element is found, else
        // returns false
        if (Ints.contains(arr, target))
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