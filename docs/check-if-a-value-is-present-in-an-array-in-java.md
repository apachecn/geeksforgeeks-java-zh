# 检查 Java 中的数组中是否存在值

> 原文:[https://www . geesforgeks . org/check-if-a-value-in-array-in-Java/](https://www.geeksforgeeks.org/check-if-a-value-is-present-in-an-array-in-java/)

给定一个数组，任务是编写一个 Java 程序来检查这个数组中是否存在特定的元素。

**示例:**

```java
Input: arr[] = [5, 1, 1, 9, 7, 2, 6, 10], key = 7
Output: true

Input: arr[] = [-1, 1, 5, 8], key = -2
Output: false
```

数组是包含一组元素的数据结构。通常，这些元素都是相同的数据类型，如整数或字符串。数组通常在计算机程序中用于组织数据，以便可以快速对一组相关的值进行排序或搜索。数组的所有项目都存储在连续的内存位置。

### 方法

有许多方法可以检查这个数组中是否有特定的元素。这些是–

*   使用线性搜索方法
*   使用二分搜索法方法
*   使用 List.contains()方法
*   使用 Stream.anyMatch()方法

### **1。使用** [**线性搜索**](https://www.geeksforgeeks.org/linear-search/) **方法:**

在这种情况下，按顺序遍历列表或数组，并检查每个元素。

**语法:**

```java
for (int element : arr) {
    if (element == toCheckValue) {
        return true;
    }
}
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to check whether
// an element is present in array or not

import java.util.Arrays;
import java.util.stream.IntStream;

class GFG {

    // Function return true if given element
    // found in array
    private static void check(int[] arr, int toCheckValue)
    {
        // check if the specified element
        // is present in the array or not
        // using Linear Search method
        boolean test = false;
        for (int element : arr) {
            if (element == toCheckValue) {
                test = true;
                break;
            }
        }

        // Print the result
        System.out.println("Is " + toCheckValue
                           + " present in the array: " + test);
    }

    public static void main(String[] args)
    {

        // Get the array
        int arr[] = { 5, 1, 1, 9, 7, 2, 6, 10 };

        // Get the value to be checked
        int toCheckValue = 7;

        // Print the array
        System.out.println("Array: "
                           + Arrays.toString(arr));

        // Check if this value is
        // present in the array or not
        check(arr, toCheckValue);
    }
}
```

**Output**

```java
Array: [5, 1, 1, 9, 7, 2, 6, 10]
Is 7 present in the array: true
```

### **2。使用** [**【二分搜索法】**](https://www.geeksforgeeks.org/binary-search/) **方法:**

在这种情况下，通过重复将搜索间隔分成两半来搜索排序的数组。从覆盖整个数组的间隔开始。如果搜索关键字的值小于间隔中间的项目，请将间隔缩小到下半部分。否则，缩小到上半部分。反复检查，直到找到值或间隔为空。
在本例中， [Arrays.binarySearch()](https://www.geeksforgeeks.org/arrays-binarysearch-java-examples-set-1/) 方法用于二分搜索法。

**语法:**

```java
public static int 
    binarySearch(data_type arr, data_type key)
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to check whether
// an element is present in array or not

import java.util.Arrays;
import java.util.stream.IntStream;

class GFG {

    // Function return true if given element
    // found in array
    private static void check(int[] arr, int toCheckValue)
    {
        // sort given array
        Arrays.sort(arr);

        // check if the specified element
        // is present in the array or not
        // using Binary Search method
        int res = Arrays.binarySearch(arr, toCheckValue);

        boolean test = res > 0 ? true : false;

        // Print the result
        System.out.println("Is " + toCheckValue
                           + " present in the array: " + test);
    }

    public static void main(String[] args)
    {

        // Get the array
        int arr[] = { 5, 1, 1, 9, 7, 2, 6, 10 };

        // Get the value to be checked
        int toCheckValue = 7;

        // Print the array
        System.out.println("Array: "
                           + Arrays.toString(arr));

        // Check if this value is
        // present in the array or not
        check(arr, toCheckValue);
    }
}
```

**Output**

```java
Array: [5, 1, 1, 9, 7, 2, 6, 10]
Is 7 present in the array: true
```