# 合并两个数组的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序-合并-两个数组/](https://www.geeksforgeeks.org/java-program-to-merge-two-arrays/)

给定两个数组，任务是**合并或连接**它们，并将结果存储到另一个数组中。

**示例:**

> ***输入** : arr1[] = { 1，3，4，5}，arr2[] = {2，4，6，8}*
> ***输出** : arr3[] = {1，3，4，5，2，4，6，8}*
> 
> ***输入** : arr1[] = { 5，8，9}，arr2[] = {4，7，8}*
> ***输出** : arr3[] = {5，8，9，4，7，8}*

**方法 1:使用预定义功能**

*   首先，我们初始化两个数组，比如数组 **a** 和数组 **b** ，然后我们将在这两个数组中存储值。
*   之后，我们将计算数组 **a** 和 **b** 的长度，并将其存储到变量中，比如说 **a1** 和 **b1** 。我们需要计算数组的长度，因为通过使用这些数组的长度，我们可以预测合并后存储元素的结果数组的长度。
*   然后通过使用 [System.arraycopy()](https://www.geeksforgeeks.org/system-arraycopy-in-java/) ，我们合并两个数组，结果将存储在第三个数组中。

下面是上述方法的实现。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to demonstrate merging
// two array using pre-defined method

import java.util.Arrays;

public class MergeTwoArrays1 {
    public static void main(String[] args)
    {
        // first array
        int[] a = { 10, 20, 30, 40 };

        // second array
        int[] b = { 50, 60, 70, 80 };

        // determines length of firstArray
        int a1 = a.length;

        // determines length of secondArray
        int b1 = b.length;

        // resultant array size
        int c1 = a1 + b1;

        // create the resultant array
        int[] c = new int[c1];

        // using the pre-defined function arraycopy
        System.arraycopy(a, 0, c, 0, a1);
        System.arraycopy(b, 0, c, a1, b1);

        // prints the resultant array
        System.out.println(Arrays.toString(c));
    }
}
```

**Output**

```java
[10, 20, 30, 40, 50, 60, 70, 80]
```

**时间复杂度:**O(M+N)
T5】辅助空间: O(M + N)

这里 M 是阵 **a** 的长度，N 是阵 **b** 的长度。

**方法二:不使用预定义函数**

*   首先，我们初始化两个数组，比如数组 **a** 和数组 **b** ，然后我们将在两个数组中存储值。
*   之后，我们将计算两个数组的长度，并将其存储到变量中，比如说 **a1** 和 **b1** 。我们需要计算数组的长度，因为通过使用这些数组的长度，我们可以预测合并后存储元素的结果数组的长度。
*   然后将创建新的数组 **c** ，这是结果数组。
*   现在，第一个循环用于将第一个数组的元素逐个存储到结果数组中，第二个 for 循环用于将第二个数组的元素逐个存储到结果数组中。
*   最后一个 for 循环用于打印结果数组的元素。

下面是上述方法的实现。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to demonstrate merging
// two array without using pre-defined method

import java.io.*;

public class MergeTwoArrays2 {
    public static void main(String[] args)
    {

        // first array
        int a[] = { 30, 25, 40 };
        // second array
        int b[] = { 45, 50, 55, 60, 65 };

        // determining length of first array
        int a1 = a.length;
        // determining length of second array
        int b1 = b.length;

        // resultant array size
        int c1 = a1 + b1;

        // Creating a new array
        int[] c = new int[c1];

        // Loop to store the elements of first
        // array into resultant array
        for (int i = 0; i < a1; i = i + 1) {
            // Storing the elements in 
            // the resultant array
            c[i] = a[i];
        }

        // Loop to concat the elements of second 
        // array into resultant array
        for (int i = 0; i < b1; i = i + 1) {

            // Storing the elements in the 
            // resultant array
            c[a1 + i] = b[i];
        }

        // Loop to print the elements of 
        // resultant array after merging
        for (int i = 0; i < c1; i = i + 1) {

            // print the element
            System.out.println(c[i]);
        }
    }
}
```

**Output**

```java
30
25
40
45
50
55
60
65

```

**时间复杂度:**O(M+N)
T5】辅助空间: O(M + N)

这里 M 是阵 **a** 的长度，N 是阵 **b** 的长度。