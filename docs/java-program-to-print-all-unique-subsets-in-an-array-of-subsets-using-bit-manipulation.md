# 使用位操作打印子集数组中所有唯一子集的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序-打印-子集数组中所有唯一子集-使用位操作/](https://www.geeksforgeeks.org/java-program-to-print-all-unique-subsets-in-an-array-of-subsets-using-bit-manipulation/)

给定唯一元素的整数数组，返回所有可能的子集(幂集)。解决方案集不能包含重复的子集，并且应该以任何顺序返回解决方案。

插图:

```
Input: array = [1,2,3]
Output: [[],[1],[2],[1,2],[3],[1,3],[2,3],[1,2,3]]
```

```
Input: array = [0]
Output: [[],[0]]
```

**接近 1**

算法

1.  生成长度为 n 的所有可能的二进制位掩码。
2.  将子集映射到每个位掩码
    *   位掩码中第 ith 位的 1 表示子集内存在 nums[i]
    *   0 表示它不存在。
3.  返回输出列表。

**实施:**

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Print all unique subsets in an array of
// subsets using bit manipulation

// Importing input output classes
import java.io.*;
// Importing utility classes
import java.util.*;

// Main class
class GFG {

    // Method 1
    // Helper method
    static List<List<Integer> > subsets(int[] nums)
    {
        List<List<Integer> > output = new ArrayList<>();
        int n = nums.length;

        for (int i = (int)Math.pow(2, n);
             i < (int)Math.pow(2, n + 1); ++i) {

            // Generate bitmask, from 0..00 to 1..11
            String bitmask
                = Integer.toBinaryString(i).substring(1);

            // Appending subset corresponding to that
            // bitmask
            List<Integer> curr = new ArrayList<>();

            for (int j = 0; j < n; ++j) {
                if (bitmask.charAt(j) == '1')

                    // Adding it to subset
                    curr.add(nums[j]);
            }

            // Adding the subset
            output.add(curr);
        }
        return output;
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Custom input integer array
        int arr[] = { 1, 2, 3 };

        // Calling method 1 in main() method
        List<List<Integer> > output = subsets(arr);

        // Printing all unique subsets in an array
        System.out.println(output);
    }
}
```

**Output**

```
[[], [3], [2], [2, 3], [1], [1, 3], [1, 2], [1, 2, 3]]
```

复杂性分析:

*   时间复杂度:-o(n×2^n)生成所有子集，然后将它们复制到输出列表中。
*   空间复杂度:-o(n×2^n)来保持长度 NN 的所有子集，因为每个 NN 元素可能存在或不存在。

**方法 2:**

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Print all unique subsets in an array of
// subsets using bit manipulation

// Importing input output classes
import java.io.*;
// Importing utility classes
import java.util.*;

// Main class
class GFG {

    // Method 1
    static List<List<Integer> > subsets(int[] nums)
    {

        // Creating List class object
        // Declaring. object of integer List
        List<List<Integer> > output = new ArrayList<>();

        int n = nums.length;

        // Increase the size by using left shift (1 * 2^n)
        int size = 1 << n;

        for (int i = 0; i < size; i++) {
            List<Integer> curr = new ArrayList<>();
            for (int j = 0; j < n; j++) {

                // right shift i and j i.e. i/2^j
                if (((i >> j) & 1) == 1) {

                    // Add it to subset
                    curr.add(nums[j]);
                }
            }

            // Adding the subset
            output.add(curr);
        }
        return output;
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {

        // Custom input array
        int arr[] = { 1, 2, 3 };

        // Calling method 1 in main() method
        List<List<Integer> > output = subsets(arr);

        // Print all unique subsets in an array
        System.out.println(output);
    }
}
```

**Output**

```
[[], [1], [2], [1, 2], [3], [1, 3], [2, 3], [1, 2, 3]]
```