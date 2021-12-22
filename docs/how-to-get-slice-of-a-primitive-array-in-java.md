# 如何在 Java 中获取一个原语数组的切片

> 原文:[https://www . geeksforgeeks . org/如何获取 java 中的原始数组切片/](https://www.geeksforgeeks.org/how-to-get-slice-of-a-primitive-array-in-java/)

给定一个基元数组，任务是使用开始和结束索引在 Java 中获取这个数组的切片。

**示例:**

```
Input: arr[] = {1, 2, 3, 4, 5}, startIndex = 2, endIndex = 4
Output: {3, 4, 5}

Input: arr[] = {1, 2, 3, 4, 5}, startIndex = 0, endIndex = 1
Output: {1, 2}

```

*   **Method 1**: Naive Method.
    1.  获取数组、起始索引和结束索引。
    2.  创建并清空大小为 endIndex-startIndex 的基元数组。
    3.  将元素从起始索引复制到结束索引，从原始数组复制到切片数组。
    4.  返回或打印数组的切片。

    下面是上述方法的实现:

    ```
    // Java program to Get a Slice
    // of a Primitive Array

    import java.util.Arrays;

    class GFG {
        // Function to get slice of a primitive array in Java
        public static int[] getSliceOfArray(int[] arr, 
                                         int start, int end)
        {

            // Get the slice of the Array
            int[] slice = new int[end - start];

            // Copy elements of arr to slice
            for (int i = 0; i < slice.length; i++) {
                slice[i] = arr[start + i];
            }

            // return the slice
            return slice;
        }
        public static void main(String[] args)
        {

            // Get the array, startIndex and endIndex
            int[] arr = { 1, 2, 3, 4, 5 };
            int start = 2, end = 4;

            // Get the slice of the array
            int[] slice = getSliceOfArray(arr, start, end + 1);

            // Print the slice of the array
            System.out.println(Arrays.toString(slice));
        }
    }
    ```

    **Output:**

    ```
    [3, 4, 5]

    ```