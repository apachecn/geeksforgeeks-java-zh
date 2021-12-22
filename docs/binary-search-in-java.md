# 爪哇的二分搜索法

> 原文:[https://www.geeksforgeeks.org/binary-search-in-java/](https://www.geeksforgeeks.org/binary-search-in-java/)

[二分搜索法](https://www.geeksforgeeks.org/binary-search/)是当输入被排序时应用的搜索技术之一，因为这里我们关注于找到作为参考框架的中间元素，无论是向左还是向右，因为元素已经被排序了。这种搜索有助于优化搜索技术，每次迭代都被称为二分搜索法，读者会对它产生压力，因为它间接应用于解决问题。现在你一定在想，如果输入没有排序，那么结果就没有定义。

> **注意:**如果有重复，不能保证会找到哪一个。

现在让我们坚持一下 ***两个函数返回的负值的显著值*** ？

函数返回搜索关键字的索引，如果它包含在数组中；否则，(-(插入点)–1)。插入点定义为将键插入数组的点:大于键的第一个元素的索引，如果数组中的所有元素都小于指定的键，则为. length。请注意，这保证了当且仅当找到键时，返回值将> = 0。

**二分搜索法在 Java 中的实现**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java implementation of recursive Binary Search
class BinarySearch
{
    // Returns index of x if it is present in arr[l..
    // r], else return -1
    int binarySearch(int arr[], int l, int r, int x)
    {
        if (r>=l)
        {
            int mid = l + (r - l)/2;

            // If the element is present at the
            // middle itself
            if (arr[mid] == x)
               return mid;

            // If element is smaller than mid, then
            // it can only be present in left subarray
            if (arr[mid] > x)
               return binarySearch(arr, l, mid-1, x);

            // Else the element can only be present
            // in right subarray
            return binarySearch(arr, mid+1, r, x);
        }

        // We reach here when element is not present
        //  in array
        return -1;
    }

    // Driver method to test above
    public static void main(String args[])
    {
        BinarySearch ob = new BinarySearch();
        int arr[] = {2,3,4,10,40};
        int n = arr.length;
        int x = 10;
        int result = ob.binarySearch(arr,0,n-1,x);
        if (result == -1)
            System.out.println("Element not present");
        else
            System.out.println("Element found at index " +
                                                 result);
    }
}
```

**Output:** 

```java
Element found at index 3
```

> **提示:**极客们你们一定想知道有没有像[下界()](https://www.geeksforgeeks.org/stdlower_bound-in-c/)或[上界()](https://www.geeksforgeeks.org/stdupper_bound-in-cpp/)这样的函数，很可能在 C++ STL 中找到。所以直截了当的答案是，直到 Java 9 才出现了函数，后来它们才被添加进来。

### **爪哇二分搜索法类型**

**在 Java 中做一个二分搜索法有两种方法**

*   Arrays.binarysearch
*   Collections.binarysearch

**类型 1:** [数组. binarysearch()](https://www.geeksforgeeks.org/arrays-binarysearch-java-examples-set-1/)

它也适用于原始数据类型的数组。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to demonstrate working of binarySearch()
// Method of Arrays class In a sorted array

// Importing required classes
import java.util.Arrays;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Declaring an integer array
        int arr[] = { 10, 20, 15, 22, 35 };

        // Sorting the above array
        // using sort() method od Arrays class
        Arrays.sort(arr);

        int key = 22;
        int res = Arrays.binarySearch(arr, key);

        if (res >= 0)
            System.out.println(
                key + " found at index = " + res);
        else
            System.out.println(key + " Not found");

        key = 40;
        res = Arrays.binarySearch(arr, key);
        if (res >= 0)
            System.out.println(
                key + " found at index = " + res);
        else
            System.out.println(key + " Not found");
    }
}
```

**Output:** 

```java
22 found at index = 3
40 Not found
```

现在让我们看看 Collections.binarySearch()是如何为 LinkedList 工作的。所以基本上如上所述，对于像 ArrayList 这样的“随机访问”列表，这个方法在 log(n)时间内运行。如果指定的列表没有实现 RandomAccess 接口并且很大，这个方法将执行一个基于迭代器的二分搜索法，执行 O(n)个链接遍历和 O(log n)个元素比较。

**类型 2:**[collections . binary search()](https://www.geeksforgeeks.org/collections-binarysearch-java-examples/)

它适用于对象集合，如[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)和[链接列表](https://www.geeksforgeeks.org/linked-list-in-java/)。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Demonstrate Working of binarySearch()
// method of Collections class

// Importing required classes
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

// Main class
public class GFG {
    // Main driver method
    public static void main(String[] args)
    {
        // Creating an empty ArrayList of integer type
        List<Integer> al = new ArrayList<Integer>();

        // Populating the Arraylist
        al.add(1);
        al.add(2);
        al.add(3);
        al.add(10);
        al.add(20);

        // 10 is present at index 3
        int key = 10;
        int res = Collections.binarySearch(al, key);

        if (res >= 0)
            System.out.println(
                key + " found at index = " + res);
        else
            System.out.println(key + " Not found");

        key = 15;
        res = Collections.binarySearch(al, key);

        if (res >= 0)
            System.out.println(
                key + " found at index = " + res);
        else
            System.out.println(key + " Not found");
    }
}
```

**Output:** 

```java
10 found at index = 3
15 Not found
```