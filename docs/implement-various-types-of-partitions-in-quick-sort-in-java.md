# 在 Java 中快速排序实现各种类型的分区

> 原文:[https://www . geesforgeks . org/implement-各种类型的分区-in-quick-sort-in-java/](https://www.geeksforgeeks.org/implement-various-types-of-partitions-in-quick-sort-in-java/)

[快速排序](https://www.geeksforgeeks.org/quick-sort/)是一个[分治](https://www.geeksforgeeks.org/divide-and-conquer-algorithm-introduction/)算法，用于对元素进行排序。在这个算法中，我们选择一个枢轴，并根据枢轴对给定的数组进行分区。快速排序算法是最常用的算法，因为该算法对缓存友好，并且对元素执行就地排序，这意味着对元素排序不需要额外的空间。

**注:**

> 快速排序算法一般是不稳定的算法，因为快速排序无法保持元素的相对
> 顺序。

**快速排序算法可以有三个分区:**

1.  **天真分区:**在这个分区中有助于保持元素的相对顺序，但是这个分区占用 O(n)个额外空间。
2.  **Lomuto 分区:**在这个分区中，最后一个元素选择作为这个分区的枢纽。在分区之后，枢轴获得其所需的位置，但是在这个分区中进行更多的比较。
3.  **霍尔的分区:**在这个分区中，第一个元素选择作为这个分区中的枢纽。枢轴在分区后移动其所需位置，但与 Lomuto 分区相比，比较较少。

**1。天真分区**

**算法:**

```java
Naivepartition(arr[],l,r)

1\. Make a Temporary array temp[r-l+1] length
2\. Choose last element as a pivot element
3\. Run two loops:
    -> Store all the elements in the temp array that are less than pivot element
    -> Store the pivot element 
    -> Store all the elements in the temp array that are greater than pivot element.
4.Update all the elements of arr[] with the temp[] array    

QuickSort(arr[], l,  r)

If r > l
     1\. Find the partition point of the array  
              m = Naivepartition(a,l,r) 
     2\. Call Quicksort for less than partition point   
             Call Quicksort(arr, l, m-1)
     3\. Call Quicksort for greater than the partition point 
             Call Quicksort(arr, m+1, r)
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate the naive partition
// in quick sort

import java.io.*;
import java.util.*;
public class GFG {
    static int partition(int a[], int start, int high)
    {
        // Creating temporary
        int temp[] = new int[(high - start) + 1];

        // Choosing a pivot
        int pivot = a[high];
        int index = 0;

        // smaller number
        for (int i = start; i <= high; ++i) {
            if (a[i] < pivot)
            {
                temp[index++] = a[i];
            }
        }

        // pivot position
        int position = index;

        // Placing the pivot to its original position
        temp[index++] = pivot;

        for (int i = start; i <= high; ++i)
        {
            if (a[i] > pivot)
            {
                temp[index++] = a[i];
            }
        }

        // Change the original array
        for (int i = start; i <= high; ++i) {
            a[i] = temp[i - start];
        }

        // return the position of the pivot
        return position;
    }

    static void quicksort(int numbers[], int start, int end)
    {
        if (start < end) {
            int point = partition(numbers, start, end);

            quicksort(numbers, start, point - 1);
            quicksort(numbers, point + 1, end);
        }
    }

    // Function to print the array
    static void print(int numbers[])
    {
        for (int a : numbers)
        {
            System.out.print(a + " ");
        }
    }

    public static void main(String[] args)
    {
        int numbers[] = { 3, 2, 1, 78, 9798, 97 };

        // rearrange using naive partition
        quicksort(numbers, 0, numbers.length - 1);

        print(numbers);
    }
}
```

**Output**

```java
1 2 3 78 97 9798 
```

**2 .洛美分区〔t1〕**

*   **Lomuto 的分割算法(**[](https://www.geeksforgeeks.org/stability-in-sorting-algorithms/)****算法)****

```java
**Lomutopartition(arr[], lo, hi)** 

    pivot = arr[hi]
    i = lo     // place for swapping
    for j := lo to hi – 1 do
        if arr[j] <= pivot then
            swap arr[i] with arr[j]
            i = i + 1
    swap arr[i] with arr[hi]
    return i

**QuickSort(arr[], l,  r)**

If r > l
     1\. Find the partition point of the array  
              m =Lomutopartition(a,l,r) 
     2\. Call Quicksort for less than partition point   
             Call Quicksort(arr, l, m-1)
     3\. Call Quicksort for greater than the partition point 
             Call Quicksort(arr, m+1, r)
```

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to demonstrate the Lomuto partition
// in quick sort

import java.util.*;
public class GFG {

    static int sort(int numbers[], int start, int last)
    {
        int pivot = numbers[last];
        int index = start - 1;
        int temp = 0;

        for (int i = start; i < last; ++i)
        {
            if (numbers[i] < pivot) {
                ++index;

                // swap the position
                temp = numbers[index];
                numbers[index] = numbers[i];
                numbers[i] = temp;
            }
        }

        int pivotposition = ++index;

        temp = numbers[index];
        numbers[index] = pivot;
        numbers[last] = temp;

        return pivotposition;
    }

    static void quicksort(int numbers[], int start, int end)
    {
        if (start < end)
        {
            int pivot_position = sort(numbers, start, end);
            quicksort(numbers, start, pivot_position - 1);
            quicksort(numbers, pivot_position + 1, end);
        }
    }

    static void print(int numbers[])
    {
        for (int a : numbers) {
            System.out.print(a + " ");
        }
    }

    public static void main(String[] args)
    {
        int numbers[] = { 4, 5, 1, 2, 4, 5, 6 };
        quicksort(numbers, 0, numbers.length - 1);
        print(numbers);
    }
}
```

****Output**

```java
1 2 4 4 5 5 6 
```** 

****3。霍尔分区****

**[霍尔的分区方案](https://en.wikipedia.org/wiki/Quicksort#Hoare_partition_scheme)的工作原理是初始化两个从两端开始的索引，这两个索引向对方移动，直到找到一个反转(左侧的值较小，右侧的值较大)。当发现反转时，交换两个值并重复该过程。**

****算法:****

```java
**Hoarepartition(arr[], lo, hi)**

   pivot = arr[lo]
   i = lo - 1  // Initialize left index
   j = hi + 1  // Initialize right index

   // Find a value in left side greater
   // than pivot
   do
      i = i + 1
   while arr[i] < pivot

   // Find a value in right side smaller
   // than pivot
   do
      j--;
   while (arr[j] > pivot);

   if i >= j then 
      return j

   swap arr[i] with arr[j]

**QuickSort(arr[], l,  r)**

If r > l
     1\. Find the partition point of the array  
              m =Hoarepartition(a,l,r) 
     2\. Call Quicksort for less than partition point   
             Call Quicksort(arr, l, m)
     3\. Call Quicksort for greater than the partition point 
             Call Quicksort(arr, m+1, r)
```

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java implementation of QuickSort
// using Hoare's partition scheme

import java.io.*;

class GFG {

    // This function takes first element as pivot, and
    // places all the elements smaller than the pivot on the
    // left side and all the elements greater than the pivot
    // on the right side. It returns the index of the last
    // element on the smaller side
    static int partition(int[] arr, int low, int high)
    {
        int pivot = arr[low];
        int i = low - 1, j = high + 1;

        while (true)
        {
            // Find leftmost element greater
            // than or equal to pivot
            do {
                i++;
            } while (arr[i] < pivot);

            // Find rightmost element smaller
            // than or equal to pivot
            do {
                j--;
            } while (arr[j] > pivot);

            // If two pointers met.
            if (i >= j)
                return j;

            // swap(arr[i], arr[j]);
            int temp = arr[i];
            arr[i] = arr[j];
            arr[j] = temp;

        }
    }

    // The main function that
    // implements QuickSort
    // arr[] --> Array to be sorted,
    // low --> Starting index,
    // high --> Ending index
    static void quickSort(int[] arr, int low, int high)
    {
        if (low < high) {

            // pi is partitioning index,
            // arr[p] is now at right place
            int pi = partition(arr, low, high);

            // Separately sort elements before
            // partition and after partition
            quickSort(arr, low, pi);
            quickSort(arr, pi + 1, high);
        }
    }

    // Function to print an array
    static void printArray(int[] arr, int n)
    {
        for (int i = 0; i < n; ++i)
            System.out.print(" " + arr[i]);

        System.out.println();
    }

    // Driver Code
    static public void main(String[] args)
    {
        int[] arr = { 10, 17, 18, 9, 11, 15 };
        int n = arr.length;
        quickSort(arr, 0, n - 1);

        printArray(arr, n);
    }
}
```

****Output**

```java
 9 10 11 15 17 18
```**