# 用示例实现 Java 中的 next _()

> 原文:[https://www . geeksforgeeks . org/implementing-next _ placement-in-Java-with-examples/](https://www.geeksforgeeks.org/implementing-next_permutation-in-java-with-examples/)

给定一个数组或字符串，任务是在 Java 中找到它的下一个更大的字典排列。

**示例:**

```java
Input: string = "gfg"
Output: ggf

Input: arr[] = {1, 2, 3}
Output: {1, 3, 2}

```

在 C++中，有一个特定的函数可以省去我们很多代码。在头文件**#中包含<算法>** 。功能是[**next _ arrange(a . begin()，a.end())**](https://www.geeksforgeeks.org/stdnext_permutation-prev_permutation-c/) 。它用于将范围[第一个，最后一个]中的元素重新排列到下一个字典顺序更大的排列中。一个排列就是 N 个中的每一个！元素可以采用的可能排列(其中 N 是该范围内的元素数量)。不同的排列可以根据它们在字典上的相互比较来排序。

显然，Java 没有提供任何这样的内置方法。因此，本文讨论了**如何在 Java 中实现下一个置换函数**及其算法。

**算法:**

1.  找到最长的非递增后缀，找到轴心。
2.  如果后缀是整个数组，则数据没有更高阶的排列。
3.  找到枢轴最右边的后继。
4.  交换继任者和轴心。
5.  反转后缀。

下面是上述方法的实现:

```java
// Java program to implement
// the next_permutation method

import java.util.Arrays;

public class nextPermutation {

    // Function to swap the data
    // present in the left and right indices
    public static int[] swap(int data[], int left, int right)
    {

        // Swap the data
        int temp = data[left];
        data[left] = data[right];
        data[right] = temp;

        // Return the updated array
        return data;
    }

    // Function to reverse the sub-array
    // starting from left to the right
    // both inclusive
    public static int[] reverse(int data[], int left, int right)
    {

        // Reverse the sub-array
        while (left < right) {
            int temp = data[left];
            data[left++] = data[right];
            data[right--] = temp;
        }

        // Return the updated array
        return data;
    }

    // Function to find the next permutation
    // of the given integer array
    public static boolean findNextPermutation(int data[])
    {

        // If the given dataset is empty
        // or contains only one element
        // next_permutation is not possible
        if (data.length <= 1)
            return false;

        int last = data.length - 2;

        // find the longest non-increasing suffix
        // and find the pivot
        while (last >= 0) {
            if (data[last] < data[last + 1]) {
                break;
            }
            last--;
        }

        // If there is no increasing pair
        // there is no higher order permutation
        if (last < 0)
            return false;

        int nextGreater = data.length - 1;

        // Find the rightmost successor to the pivot
        for (int i = data.length - 1; i > last; i--) {
            if (data[i] > data[last]) {
                nextGreater = i;
                break;
            }
        }

        // Swap the successor and the pivot
        data = swap(data, nextGreater, last);

        // Reverse the suffix
        data = reverse(data, last + 1, data.length - 1);

        // Return true as the next_permutation is done
        return true;
    }

    // Driver Code
    public static void main(String args[])
    {
        int data[] = { 1, 2, 3 };
        if (!findNextPermutation(data))
            System.out.println("There is no higher"
                               + " order permutation "
                               + "for the given data.");
        else {
            System.out.println(Arrays.toString(data));
        }
    }
}
```

**Output:**

```java
[1, 3, 2]

```