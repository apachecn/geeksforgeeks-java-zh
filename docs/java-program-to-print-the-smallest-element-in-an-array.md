# 打印数组中最小元素的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序打印数组中最小的元素/](https://www.geeksforgeeks.org/java-program-to-print-the-smallest-element-in-an-array/)

**Java** 提供了一个数据结构，数组，存储了相同类型的数据集合。它是相同类型元素的固定大小的顺序集合。

**例:**

```
arr1[] = {2 , -1 , 9 , 10}
output : -1

arr2[] = {0, -10, -13, 5}
output : -13
```

**我们需要在这个程序中找到并打印一个数组的最小值元素。**

1.  By maintaining a **min element** and updating it when traversing the whole array, if we encounter a number less than min.
2.  Sort an array by **and print the 0th index element of the sorted array.**

**方法 1:** 维护一个**最小元素**，如果我们遇到一个小于最小的数，在遍历整个数组时更新它。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to print the smallest element of the array

public class FindSmallestElementInArray {
    public static void main(String[] args)
    {

        // Either we can initialize array elements or can
        // get input from user. Always it is best to get
        // input from user and form the array
        int[] initializedArray
            = new int[] { 25, 110, 74, 75, 5 };

        System.out.println("Given array ");

        for (int i = 0; i < initializedArray.length; i++) {

            System.out.println(initializedArray[i]);
        }

        // Initialize minValue with first element of array.
        int minValue = initializedArray[0];

        // Loop through the array
        for (int i = 0; i < initializedArray.length; i++) {

            // Compare elements of array with minValue and
            // if condition true, make minValue to that
            // element

            if (initializedArray[i] < minValue)

                minValue = initializedArray[i];
        }

        System.out.println(
            "Smallest element present in given array: "
            + minValue);
    }
}
```

**Output**

```
Given array 
25
110
74
75
5
Smallest element present in given array: 5
```

*   **时间复杂度:** O(n)
*   **空间复杂度:** O(1)

**方法 2:** 通过**对数组**进行排序，并在排序后打印数组的第 0 个索引元素。

## Java

```
// Java program to print the smallest element of the array

import java.util.*;

public class FindSmallestElementInArray {
    public static void main(String[] args)
    {

        // we can initialize array elements
        int[] initializedArray = new int[] { 25, 110, 74, 75, 5 };

        System.out.println("Given array ");
        for (int i = 0; i < initializedArray.length; i++) {

            System.out.println(initializedArray[i]);
        }

        // sort the array
        Arrays.sort(initializedArray);

        int minValue = initializedArray[0];

        System.out.println(
            "Smallest element present in given array: "
            + minValue);
    }
}
```

**输出**

```
Given array 
25
110
74
75
5
Smallest element present in given array: 5
```

*   **Time complexity:** o (NlogN) Since the time spent sorting is nlogn, there are n elements in the array.
*   **Spatial complexity:** o (1)

。