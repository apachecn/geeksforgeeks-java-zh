# 使用 Java 中的位集从整数数组中查找缺失的数字

> 原文:[https://www . geesforgeks . org/find-整数数组中缺少数字-使用-bitset-in-java/](https://www.geeksforgeeks.org/finding-missing-number-from-integer-array-using-bitset-in-java/)

给定一个从 1 到 n 的整数数组，要求您从数组中找到缺少的数字。

**例:**

```
Input : n = 5, a[] = {1, 2, 4, 5}
Output: 3
Explanation: From the array of numbers 1 to 5, 3 is missing.

Input : n = 10, a[] = {1, 3, 4, 6, 8, 10}
Output: 2, 5, 7, 9
Explanation: From the array of numbers 1 to 10, 2, 5, 7 and 9 are missing.

```

这个问题很容易解决，通过计算 n 个数的和，用公式，

```
sum = (n * (n + 1)) / 2

```

在[这篇](https://www.geeksforgeeks.org/find-the-missing-number/)文章中给出了这种方法的解决方案。

但是，该方法不能用于数组包含多个缺失数字的情况。

对于这种情况，Java 中的 BitSet 实用程序类可以用来解决这个问题。

**方法:**

1.  Find the number of missing elements in a given array, *misscnt* .
2.  Create a BitSet class object with *n* as the parameter.
3.  For each number in a given array, use the [bitset.set ()](https://www.geeksforgeeks.org/java-util-bitset-set-method-java/) method to set its penultimate digit to true.
4.  Initialize an integer variable [T0】 lastmissionindex, and stores the index of the last missing element.
5.  Use the loop from 0 to *misscnt* , use the [bitset. nextclearbit ()](https://www.geeksforgeeks.org/java-bitset-nextclearbit/) method, and find the first bit set to false from [T4】 lastmismissindex 【T5].
6.  是吗*负荷率指数*阿久 1 个，朝比奈。

下面是上述方法的实现

T3】JavaT5

```
// Java Program to find the missing elements
// from integer array using BitSet class

import java.io.*;
import java.util.*;

public class FindMissingNo {
    private static void findMissingNumbers(int arr[], int n)
    {
        int missCnt = n - arr.length;
        // create Bitset object b
        BitSet b = new BitSet(n);
        for (int i : arr) {
            b.set(i - 1);
        }
        int lastMissIndex = 0;
        for (int i = 0; i < missCnt; ++i) {
            lastMissIndex = b.nextClearBit(lastMissIndex);
            // print missing number
            System.out.println(++lastMissIndex);
        }
    }
    public static void main(String[] args)
    {
        int n = 10;
        // array of 10 numbers
        int[] arr = new int[] { 1, 2, 4, 6, 8, 9 };
        // call function
        findMissingNumbers(arr, n);
    }
}
```

T6T8**输出**T1

本文由 **Nithiyashree M G** 供稿。