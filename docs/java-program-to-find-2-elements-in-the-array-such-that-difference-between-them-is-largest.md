# Java 程序在数组中找到 2 个元素，使它们之间的差异最大

> 原文:[https://www . geesforgeks . org/Java-program-to-find-2-数组中的元素-它们之间的差异最大/](https://www.geeksforgeeks.org/java-program-to-find-2-elements-in-the-array-such-that-difference-between-them-is-largest/)

一个[](https://www.geeksforgeeks.org/introduction-to-arrays/)**数组是设计用来存储和访问一组对象的最高效的数据结构。给定一个整数数组，我们的任务是从该数组中找出两个元素，使它们之间的差值最大。**

****我们将讨论两种方法:****

***   Run two cycles to compare and check the differences between each possible pair.*   By calculating the minimum and maximum values of an array and returning the difference between them.**

 ```java
Input : arr = {2, 3, 10, 6, 4, 8, 1}
Output : Two elements with largest difference: 10 and 1
Explanation : The maximum difference is between 10 and 1.

Input : arr = {-7, 9, 5, 6, 3, 2}
Output : Two elements with largest difference:  9 and -7
Explanation : The maximum difference is between 9 and -7.

Input : arr = {10, 11, 88, 2, 12, 120}
Output : Two elements with largest difference:  2 and 120
Explanation : The maximum difference is between 2 and 120.
```

**方法 1:** 通过运行两个循环来比较和检查每个可能的对之间的差异

*   At the same time, the difference value is compared with the currently calculated maximum difference value.
*   Check all possible differences between any two elements in the array, and finally select the element with the largest difference.

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Find 2
// Elements in an array
// such that the difference
// between them is the largest

import java.io.*;

class Largest_Difference_GFG {
    public static int[] Maximum_Diff(int a[], int n)
    {
        int diff, greatest_diff = a[1] - a[0];
        int ele1 = a[1], ele2 = a[0];

        // Array to store the difference and the
        // two elements ele1 and ele2 .
        int res[] = new int[3];

        // Check for all possible difference between
        // any 2 elements in the array and finally select
        // the elements whose difference is the largest
        for (int i = 0; i < n; i++) {
            for (int j = i + 1; j < n; j++) {
                diff = Math.abs(a[i] - a[j]);
                if (diff > greatest_diff) {
                    greatest_diff = diff;
                    ele1 = a[i];
                    ele2 = a[j];
                }
            }
        }
        res[0] = greatest_diff;
        res[1] = ele1;
        res[2] = ele2;

        return (res);
    }
    public static void main(String[] args)
    {

        int arr[] = { 10, 11, 88, 2, 12, 120 };

        int size = arr.length;
        int[] result;

        result = Largest_Difference_GFG.Maximum_Diff(arr,
                                                     size);

        System.out.println("Greatest Difference:"
                           + result[0]);
        System.out.println(
            "Two elements with largest difference: "
            + result[1] + " and " + result[2]);
    }
}
```

**Output**

```java
Greatest Difference:118
Two elements with largest difference: 2 and 120

```

*   **时间复杂度** : O(n^2)
*   **辅助空间** : O(1)

**方法 2:** 通过计算数组的最小值和最大值并返回它们之间的差值

*   The maximum difference between two elements in an array is always the absolute difference between the smallest and largest elements in the array.
*   Use two independent for loops to determine the minimum and maximum elements of the array. The following is the implementation of the above method:

## Java

```java
// Java Program to Find 2
// Elements in an array
// such that the difference
// between them is the largest
import java.util.*;
class GFG {

    public static void main(String args[])
    {
        int array[] = new int[] { 10, 11, 88, 2, 12, 120 };
        int len = array.length;

        Arrays.sort(array); // sorting the array
        int max_diff = array[len - 1] - array[0];
        System.out.println("Maximum Difference is: "
                           + max_diff);
        System.out.println(
            "Two elements with largest difference: "
            + array[0] + " and " + array[len - 1]);
    }
}
```

**输出**

```java
Maximum Difference is: 118
Two elements with largest difference: 2 and 120

```

*   **Time complexity** : o (n)
*   **auxiliary space** : o (1)

**注意:**上述代码中的最小值和最大值元素也可以通过将数组的每个元素与最小值和最大值进行比较并相应地更新来在单个 for 循环中确定。这样，单个 for 循环可以同时返回 minValue 和 maxValue，代码行数将会减少。**