# 用递归求 N 个数之和的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序-使用递归查找 n 个数字的和/](https://www.geeksforgeeks.org/java-program-to-find-sum-of-n-numbers-using-recursion/)

[](https://www.geeksforgeeks.org/recursion/)**递归是一个过程，通过这个过程，一个函数反复调用自己，直到它落在基础条件下，我们的动机就达到了。**

**要使用递归解决任何问题，我们只需遵循以下步骤:**

1.  **从与较大/原始问题相似的问题中假设/识别**较小的问题**。**
2.  **决定最小有效输入或最小无效输入的答案，作为我们的**基础条件。****
3.  **逼近解，将答案与递归函数给出的较小问题联系起来，用它找到**较大/原问题**的答案。**

**在这里，我们说明了使用递归的总和可以通过将数字存储在数组中，并使用递归对所有数字求和来完成。**

****例****

```
**Input:** N = 5, arr[] = {70, 60, 90, 40, 80}
**Output:** Total Sum = 340

**Input:** N = 8, arr[] = {8, 7, 6, 5, 4, 3, 2, 1}
**Output:** Total Sum = 36
```

****进场:****

**现在，我们将应用上面讨论的方法递归地计算所有元素的总和。**

*   ****较小的问题**将是从索引 1 到最后一个索引的数组。**
*   ****基本条件**将是索引将达到数组长度的时间。即数组之外，这意味着不存在元素，因此返回的总和应为 0。**
*   **现在，我们的任务是使用**小问题计算出的**结果来解决**大/原问题。**这样做，因为我们知道更小的问题是从 index1 到最后一个 index，所以如果我们得到这个问题的和，然后对于整个数组的和，我们只需要将第一个元素/ ith 元素添加到那个答案中，并返回我们的最终答案。**

**下面是上述方法的实现。**

****示例:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java program to calculate the sum of
// the elements of the array recursively

import java.io.*;

class GFG {
    // recursive function
    public static int calculate_sum_using_recursion(int arr[], int i,
                                  int length)
    {
        // base condition - when reached end of the array
        // return 0
        if (i == length) {
            return 0;
        }

        // recursive condition - current element + sum of
        // (n-1) elements

        return arr[i]
         + calculate_sum_using_recursion(arr, i + 1,length);

    }

    public static void main(String[] args)
    {

        int N = 5, total_sum = 0;

        // create 1-D array to store numbers
        int arr[] = { 89, 75, 82, 60, 95 };

        // call function to calculate sum
        total_sum = calculate_sum_using_recursion(arr, 0, N);

        // print total sum
        System.out.println("The total of N numbers is : "
                           + total_sum);
    }
}
```

****Output**

```
The total of N numbers is : 401
```** 

****方法 2:****

**我们不仅可以通过一种方法应用递归，还可以通过一种或多种方法使用递归来解决一个问题。**

**在上面的**方法中，**我们从向前的方向开始递归，并在结束/最后的位置到达并达到基本条件。**

**在**这种方法中，**我们将函数中的长度变量视为变化参数，其中长度变量将从最后一个位置开始，基本情况将达到-1 的前界索引。**

****示例:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java program to calculate the sum of
// the elements of array using recursion

import java.io.*;

class GFG {

    // recursive function
    public static int calculate_sum_using_recursion(int arr[], int length)
    {
        // base condition - when reached -1 index
        // return 0
        if (length == -1) {
            return 0;
        }

        // recursive condition - current element + sum of
        // (n-1) elements
        return arr[length]
            + calculate_sum_using_recursion(arr,length - 1);

    }

    public static void main(String[] args)
    {
        int N = 8, total_sum = 0;

        // create 1-D array to store numbers
        int arr[] = { 8, 7, 6, 5, 4, 3, 2, 1 };

        // call function to calculate sum
        total_sum = calculate_sum_using_recursion(arr, N - 1);

        // print total sum
        System.out.println("The total of N numbers is : "
                           + total_sum);
    }
}
```

****Output**

```
The total of N numbers is : 36
```**