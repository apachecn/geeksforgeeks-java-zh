# 在数组列表上执行二分搜索法的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-performance-binary-search-on-ArrayList/](https://www.geeksforgeeks.org/java-program-to-perform-binary-search-on-arraylist/)

[**数组列表**](https://www.geeksforgeeks.org/arraylist-in-java/) 类是集合框架的一部分，存在于 java.util 包中。它在 java 中为我们提供了可调整大小的或动态的数组。它比标准数组慢得多，但在一些程序中很有帮助，在这些程序中，我们需要编写更简洁、更短的代码，并且需要对数组进行大量操作。

在排序数组中搜索元素最有效的算法是[二进制搜索算法](https://www.geeksforgeeks.org/binary-search/)。在本文中，我们将使用 Java 数组列表来实现这一点。

**接近:**

在 java ArrayList 上实现二分搜索法有三种方法，下面列出了这三种方法，简要介绍了实现部分的一个 java 示例所遵循的概念。

1.  迭代二分搜索法(使用循环的正常二分搜索法)
2.  递归二分搜索法(二分搜索法使用[递归](https://www.geeksforgeeks.org/recursion/))
3.  使用 java [集合的内置 binarySearch 方法。](https://www.geeksforgeeks.org/collections-in-java-2/)

**方法 1:迭代二分搜索法**

在这种方法中，我们在一次比较后忽略一半的元素。当数组被排序时。

*   将要搜索的给定值与中间元素进行比较。
*   如果它与中间元素匹配，我们返回 x。
*   如果它大于中间元素，那么对右子阵列做同样的操作，也就是说，阵列的大小减少到一半，我们剩下来比较的阵列是右子阵列。
*   如果它小于中间元素，那么对左子阵列做同样的操作，也就是说，阵列的大小减少到一半，我们剩下来比较的阵列是左子阵列。
*   如果我们除了搜索结束之外没有返回任何东西，那么返回-1，这意味着该元素不在该数组中。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to print binary search over an ArrayList

import java.io.*;
import java.util.*;

class BinarySearch 
{ 
    // Returns index of x if it is present in arr[], 
    // else return -1 
    int binarySearch(ArrayList<Integer> arr, int x) 
    { 
        int left = 0, right = arr.size() - 1; 

        while (left <= right)
        { 
            int mid = left + (right - left) / 2; 

            // Check if x is present at mid 
            if (arr.get(mid) == x) 
                return mid; 

            // If x greater, ignore left half 
            if (arr.get(mid) < x) 
                left = mid + 1; 

            // If x is smaller, ignore right half 
            else
                right = mid - 1; 
        } 

        // if we reach here, then element was 
        // not present 
        return -1; 
    } 

    // Driver method to test above 
    public static void main(String args[]) 
    { 
        BinarySearch ob = new BinarySearch(); 

        ArrayList<Integer> arr = new ArrayList<Integer>();

        arr.add(5);
        arr.add(10);
        arr.add(15);
        arr.add(20);
        arr.add(25);
        arr.add(30);
        arr.add(35); 

        int x = 10; 

        // Printing elements of array list
        System.out.println("The elements of the arraylist are: "+arr);

        int result = ob.binarySearch(arr, x); 

        if (result == -1) 
            System.out.println("Element not present"); 

        else
            System.out.println("The Element " + x + " is found at "
                               + "index " + result); 
    } 
} 
```

**Output**

```java
The elements of the arraylist are: [5, 10, 15, 20, 25, 30, 35]
The Element 10 is found at index 1
```

**方法二:递归二分搜索法**

*   将待搜索元素 t(x)与中间元素进行比较。
*   如果 x 与中间元素匹配，我们返回中间索引。
*   否则如果 x 大于中间元素，那么 x 只能位于中间元素之后的右半子阵列中。所以我们重复右半部分。
*   否则(x 较小)在左半部分重复出现。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java implementation of recursive Binary Search

import java.io.*;
import java.util.*;

class BinarySearch
{ 
    // Returns index of x if it is present in arr[l.. 
    // r], else return -1 

    int binarySearch(ArrayList<Integer> arr, int l, int r, int x) 
    { 
        if (r >= l)
        { 
            int mid = l + (r - l) / 2; 

            // If the element is present at the 
            // middle itself 
            if (arr.get(mid) == x) 
                return mid; 

            // If element is smaller than mid, then 
            // it can only be present in left subarray 
            if (arr.get(mid) > x) 
                return binarySearch(arr, l, mid - 1, x); 

            // Else the element can only be present 
            // in right subarray 
            return binarySearch(arr, mid + 1, r, x); 
        } 

        // We reach here when element is not present 
        // in array 
        return -1; 
    } 

    // Driver method to test above 
    public static void main(String args[]) 
    { 
        BinarySearch ob = new BinarySearch(); 

        ArrayList<Integer> arr = new ArrayList<Integer>();
        arr.add(5);
        arr.add(10);
        arr.add(15);
        arr.add(20);
        arr.add(25);
        arr.add(30);
        arr.add(35); 

        int n = arr.size();

        // We will find x inside the arraylist
        int x = 10; 

        // Printing elements of array list
        System.out.println("The elements of the arraylist are: "+arr);

        int result = ob.binarySearch(arr,0,n-1,x); 

        if (result == -1) 
            System.out.println("Element not present"); 
        else
            System.out.println("The Element " + x + " is found at "
                               + "index " + result); 
    } 
}
```

**Output**

```java
The elements of the arraylist are: [5, 10, 15, 20, 25, 30, 35]
The Element 10 is found at index 1
```

**方法 3:使用集合类的内置 binarySearch 方法**

在这个方法中，我们只需要调用 collections 框架的 [binarySearch()方法](https://www.geeksforgeeks.org/collections-binarysearch-java-examples/)，并将我们排序后的 ArrayList 和要搜索的值解析到这个方法中，这将返回元素的索引(如果存在)，否则返回-1。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate the searching of
// an element in ArrayList using binarySearch() 
// of Collections class

import java.util.ArrayList;
import java.util.Collections;

public class BinarySearch {

    public static void main(String[] args)
    {
        ArrayList<Integer> arr = new ArrayList<Integer>();

        arr.add(5);
        arr.add(10);
        arr.add(15);
        arr.add(20);
        arr.add(25);
        arr.add(30);
        arr.add(35); 

        // Initializing the key to be found.
        int val = 10; 

        // Printing elements of array list
        System.out.println("The elements of the arraylist are: "+arr);

        // Implementing the built-in binarySearch method from collections
        int result = Collections.binarySearch(arr,val);

        if (result == -1) 
            System.out.println("Element not present"); 
        else
            System.out.println("The Element " + val + " is found at "
                               + "index " + result); 
    } 
}
```

**Output**

```java
The elements of the arraylist are: [5, 10, 15, 20, 25, 30, 35]
The Element 10 is found at index 1
```