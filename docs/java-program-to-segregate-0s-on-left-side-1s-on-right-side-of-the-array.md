# Java 程序在数组的左侧隔离 0&在右侧隔离 1

> 原文:[https://www . geesforgeks . org/Java-program-to-separate-0s-on-左侧-1s-on-右侧-阵列/](https://www.geeksforgeeks.org/java-program-to-segregate-0s-on-left-side-1s-on-right-side-of-the-array/)

给你一个随机排列的 0 和 1 的数组。将阵列左侧的 0 和右侧的 1 分开。基本目标是遍历数组元素并以分隔 0 和 1 的方式进行排序。

插图:

> 输入数组= [0，1，0，1，0，0，1，1，1，0]
> 
> 输出数组= [0，0，0，0，0，1，1，1，1，1]

**接近:**

1.  **通过计数使用分离**
2.  **使用数组排序**
3.  **使用指针**

下面将详细讨论这三种方法:

**方法 1:**

*   计算 0 的数量。
*   遍历整个数组，寻找出现零的索引
*   保持计数并随着 0 的出现而递增
*   将所有零打印到前面
*   剩余的 1 将是 1-(0 的总数)
*   打印剩余的元素

下面是使用上述算法分离 0 和 1 的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to Segregate 0s and 1s in an array

// Importing generic libraries
import java.util.*;
// Importing Array libraries
import java.util.Arrays;

public class GFG {

    // Function to segregate 0s and 1s
    static void segregate0and1(int arr[], int n)
    {
        // Counts the no of zeros in array
        int count = 0;

        // Iteration over array
        for (int i = 0; i < n; i++) {
            if (arr[i] == 0)

                // Incrementing the count
                count++;
        }

        // Loop fills the arr with 0 until count
        for (int i = 0; i < count; i++)
            arr[i] = 0;

        // Loop fills remaining arr space with 1
        for (int i = count; i < n; i++)
            arr[i] = 1;
    }

    // Function to print segregated array
    static void print(int arr[], int n)
    {
        System.out.print("Array after segregation is ");

        // Iteration over array
        for (int i = 0; i < n; i++)
            System.out.print(arr[i] + " ");
    }

    // Main driver function
    public static void main(String[] args)
    {
        // Array taken for consideration
        int arr[] = new int[] { 0, 1, 0, 1, 1, 1 };

        // Using inbuilt function to store array size
        int n = arr.length;

        // Calling function that segregates array
        segregate0and1(arr, n);

        // Printing the above segregated array
        print(arr, n);
    }
}
```

**输出:**

```java
Array after segregation is 0 0 1 1 1 1 
```

时间复杂度:0(n)

**方法 2:使用 sort()函数**

[**sort()**](https://www.geeksforgeeks.org/arrays-sort-in-java-with-examples/) **是** 一个 方法是一个[Java . util . arrays](https://www.geeksforgeeks.org/array-class-in-java/)类方法。

**语法:**

```java
public static void sort(int[] arr, int from_Index, int to_Index)
```

**参数:**

```java
arr        - the array to be sorted
from_Index - the index of the first element, inclusive, to be sorted
to_Index   - the index of the last element, exclusive, to be sorted
```

**返回类型:**

```java
This method doesn't return any value
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to Segregate 0s and 1s in an array

// Importing generic libraries
import java.util.*;

public class GFG {

    // Function to print segregated array
    // Taking arguments- array and array size
    static void print(int arr[], int n)
    {
        System.out.print("Array after segregation is ");

        // Iteration over array
        for (int i = 0; i < n; ++i)

            // Printing array elements
            System.out.print(arr[i] + " ");
    }

    // Main driver function
    public static void main(String[] args)
    {
        // Array taken for consideration
        int arr[] = new int[] { 0, 1, 0, 1, 1, 1 };

        // Using length inbuilt function to
        int n = arr.length;

        // Using sort inbuilt function
        Arrays.sort(arr);

        // Printing elements after executing sorting
        print(arr, n);
    }
}
```

**输出:**

```java
Array after segregation is 0 0 1 1 1 1 
```

时间复杂性

**方法 3:** 保持左指针，当在数组中找到零时，与左指针的位置交换，并增加左指针。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to Segregate 0s and 1s in an array

// Importing generic libraries
import java.util.*;
import java.io.*;

class GFG {

    // Print function outside main to print elements
    static void print(int a[])
    {

        System.out.print("Array after segregation is: ");

        // Iteration over array using array
        // class inbuilt function .length()
        for (int i = 0; i < a.length; ++i) {

            // Printing elements in array
            System.out.print(a[i] + " ");
        }
    }

    // Main driver method
    public static void main(String[] args)
    {
        // Random array taken for consideration
        int a[] = { 1, 1, 0, 0, 0, 0, 1, 1 };

        // Maintaining left pointer
        int left = 0;

        // Iteration over array using length function
        for (int i = 0; i < a.length; ++i) {

            // If zeros are present
            if (a[i] == 0) {

                // Swap the elements using
                // temporary variable
                int temp = a[left];
                a[left] = a[i];
                a[i] = temp;

                // Pre incrementing left pointer
                ++left;
            }
        }

        // Calling above function to
        // print updated array
        print(a);
    }
}
```

**输出:**

```java
Array after segregation is: 0 0 0 0 1 1 1 1 
```

**时间复杂度** O(n)