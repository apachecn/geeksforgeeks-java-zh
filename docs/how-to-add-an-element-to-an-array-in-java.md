# 如何在 Java 中给数组添加元素？

> 原文:[https://www . geesforgeks . org/如何在 java 中向数组添加元素/](https://www.geeksforgeeks.org/how-to-add-an-element-to-an-array-in-java/)

给定一个大小为 n 的数组，任务是用 Java 在这个数组中添加一个元素 x。

在 Java 中不能像在 C/C++中那样动态改变数组的大小。因此，为了在数组中添加元素，可以使用以下方法之一:

1.  **By creating a new array:**
    *   创建一个大小为 n+1 的新数组，其中 n 是原始数组的大小。
    *   将原始数组的 n 个元素加到这个数组中。
    *   在第 n+1 个位置添加新元素。
    *   打印新数组。

    下面是上述方法的实现:

    ```java
    // Java Program to add an element in an Array

    import java.io.*;
    import java.lang.*;
    import java.util.*;

    class GFG {

        // Function to add x in arr
        public static int[] addX(int n, int arr[], int x)
        {
            int i;

            // create a new array of size n+1
            int newarr[] = new int[n + 1];

            // insert the elements from
            // the old array into the new array
            // insert all elements till n
            // then insert x at n+1
            for (i = 0; i < n; i++)
                newarr[i] = arr[i];

            newarr[n] = x;

            return newarr;
        }

        // Driver code
        public static void main(String[] args)
        {

            int n = 10;
            int i;

            // initial array of size 10
            int arr[]
                = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };

            // print the original array
            System.out.println("Initial Array:\n"
                               + Arrays.toString(arr));

            // element to be added
            int x = 50;

            // call the method to add x in arr
            arr = addX(n, arr, x);

            // print the updated array
            System.out.println("\nArray with " + x
                               + " added:\n"
                               + Arrays.toString(arr));
        }
    }
    ```

    **Output:**

    ```java
    Initial Array:
    [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

    Array with 50 added:
    [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 50]

    ```

2.  **通过使用数组列表作为中间存储:**

    ```java
    // Java Program to add an element in an Array

    import java.io.*;
    import java.lang.*;
    import java.util.*;

    class GFG {

        // Function to add x in arr
        public static Integer[] addX(int n, Integer arr[], int x)
        {
            int i;

            // create a new ArrayList
            List<Integer> arrlist
                = new ArrayList<Integer>(
                    Arrays.asList(arr));

            // Add the new element
            arrlist.add(x);

            // Convert the Arraylist to array
            arr = arrlist.toArray(arr);

            // return the array
            return arr;
        }

        // Driver code
        public static void main(String[] args)
        {

            int n = 10;
            int i;

            // initial array of size 10
            Integer arr[]
                = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };

            // print the original array
            System.out.println("Initial Array:\n"
                               + Arrays.toString(arr));

            // element to be added
            int x = 50;

            // call the method to add x in arr
            arr = addX(n, arr, x);

            // print the updated array
            System.out.println("\nArray with " + x
                               + " added:\n"
                               + Arrays.toString(arr));
        }
    }
    ```

    **输出:**

    ```java
    Initial Array:
    [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

    Array with 50 added:
    [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 50]

    ```

    *   使用 [asList()](https://www.geeksforgeeks.org/arrays-aslist-method-in-java-with-examples/) 方法，用原始数组创建一个[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)。
    *   只需使用 [add()](https://www.geeksforgeeks.org/java-util-arraylist-add-method-java/) 方法在列表中添加所需的元素
    *   使用[至](https://www.geeksforgeeks.org/arraylist-array-conversion-java-toarray-methods/)方法将列表转换为数组