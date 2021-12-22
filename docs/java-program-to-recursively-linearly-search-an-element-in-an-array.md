# 递归线性搜索数组中元素的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-recursive-linear-search-in-a-element-in-array/](https://www.geeksforgeeks.org/java-program-to-recursively-linearly-search-an-element-in-an-array/)

给定 n 个元素的数组 arr[]，编写一个函数来递归搜索 arr[]中的给定元素 x。

插图:

```java
Input  : arr[] = {25, 60, 18, 3, 10}
Output : Element to be searched : 3

Input  : arr[] = {10,20,30,24,15,40}
Output : -1
For x = 35
Element x is not present in arr[]
```

**程序:**

其思想是递归地从数组的两边搜索元素。如果需要搜索的元素与左边界最左边的元素匹配，或者与右边界最右边的元素匹配，则直接返回该元素的位置，否则重复剩余数组搜索与 x 值相同的元素。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Search an element in an Array Recursively

// Main class
public class GFG {

    // Method 1
    // Recursive method to search for an element and
    // its index in the array
    static int recursiveSearch(int arr[], int l, int r,
                               int x)
    {

        // if r<l,it means that element is not present in
        // the array
        if (r < l)
            return -1;

        if (arr[l] == x)
            return l;

        if (arr[r] == x)
            return r;

        // Since element has not found on both left most and
        // rightmost boundary,ie at l and r, now recurse the
        // array to find position of x.
        return recursiveSearch(arr, l + 1, r - 1, x);
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Element to be searched for
        // Custom input number
        int x = 3;

        // Declaring and initializing the integer array
        int arr[] = new int[] { 25, 60, 18, 3, 10 };

        // Calling the above recursive method method to
        // search for the element in the array

        // Recursive function is called over array to
        // get the index of the element present in an array
        int index
            = recursiveSearch(arr, 0, arr.length - 1, x);

        // If index is found means element exists
        if (index != -1)

            // Print the element and its index
            System.out.println("Element " + x
                               + " is present at index "
                               + index);

        // If we hit else case means
        // element is not present in the array
        else

            // Simply display the corresponding element
            // is not present
            System.out.println("Element " + x
                               + " is not present");
    }
}
```

**Output**

```java
Element 3 is present at index 3
```