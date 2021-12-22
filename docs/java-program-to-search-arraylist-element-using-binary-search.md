# 使用二分搜索法搜索数组列表元素的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到搜索-数组列表-元素-使用-二进制-搜索/](https://www.geeksforgeeks.org/java-program-to-search-arraylist-element-using-binary-search/)

线性搜索可用于数据结构特定数据结构的排序和非排序元素，但平均案例时间复杂度为 0(n)。然而，由于二分搜索法只能在项目按排序顺序排列并且平均情况时间复杂度为 0(logn)并且两个横向都具有最佳情况时间复杂度为 0(1)时实现。现在，给定一个包含排序元素的数组列表，检查该元素是否存在于数组列表中。

在[线性数据结构](https://www.geeksforgeeks.org/binary-search/)中搜索元素时有两种类型的横向。

1.  [线性搜索](https://www.geeksforgeeks.org/linear-search/)
2.  [二分搜索法](https://www.geeksforgeeks.org/binary-search/)。

插图:

```java
Input:

ArrayList:[1, 2, 3, 4, 6, 7, 8, 9]
key:3

Output:
true
```

**案例 1:** 使用[二分搜索法](https://www.geeksforgeeks.org/binary-search/)因为列表是按顺序排序的，与线性搜索相比，二分搜索法的平均时间复杂度更低，即 O(logn)。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Search ArrayList Element
// Using Binary Search

// Importing generic java libraries
import java.io.*;
import java.util.*;

class GFG {

    // Method to search elements in ArrayList
    static boolean search(int key, ArrayList<Integer> A)
    {
        // low pointer
        int low = 0;

        // high pointer
        int high = A.size() - 1;

        while (low <= high) {

            // find the mid pointer
            int mid = low + (high - low) / 2;
            if (A.get(mid) == key) {
                return true;
            }
            else if (A.get(mid) < key) {

                // shift the low pointer
                low = mid + 1;
            }
            else {

                // shift the high pointer
                high = mid - 1;
            }
        }
        return false;
    }

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an ArrayList
        ArrayList<Integer> A = new ArrayList<>();

        // Adding items in the list
        A.add(1);
        A.add(2);
        A.add(3);
        A.add(4);
        A.add(6);
        A.add(7);
        A.add(8);
        A.add(9);

        // Random element to be searched
        int key = 19;

        // Binary search
        boolean check = search(key, A);

        System.out.println(check);

        int key1 = 2;

        // Binary search
        boolean check1 = search(key1, A);

        System.out.println(check1);
    }
}
```

**输出:**

```java
false
true
```

**情况 2:** 假设为了找到最大元素的最大索引小于使用二分搜索法的数组列表的排序重复元素中的键。

```java
Input:

List: [2, 3, 3, 4, 4, 5, 6, 7]
key: 2
key: 4

Output:
-1
2
```

**示例:**根据条件修改二分搜索法

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Search ArrayList Element
// Using Binary Search

// Importing generic java libraries
import java.io.*;
import java.util.*;

class GFG {

    // Method to search elements in arrayList
    static int search(int key, ArrayList<Integer> A)
    {
        // Low pointer
        int low = 0;

        // High pointer
        int high = A.size() - 1;
        int index = -1;
        while (low <= high) {

            // Mid pointer
            int mid = low + (high - low) / 2;
            if (A.get(mid) == key) {

                // Shift the High Pointer
                high = mid - 1;
            }
            else if (A.get(mid) < key) {

                // Storing the index of mid index value
                index = mid;

                // Shift the Low Pointer
                low = mid + 1;
            }

            else {
                high = mid - 1;
            }
        }

        // Return the index
        return index;
    }

    public static void main(String[] args)
    {
        // Creating an ArrayList
        ArrayList<Integer> A = new ArrayList<>();

        // Adding elements in ArrayList
        A.add(2);
        A.add(3);
        A.add(3);
        A.add(4);
        A.add(4);
        A.add(5);
        A.add(6);
        A.add(7);

        // Key
        int key = 5;

        // Index of smallest greater element
        int index = search(key, A);

        // Print searched element
        System.out.println(index);
    }
}
```

**输出:**

```java
4
```