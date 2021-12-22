# 在 Java 中查找排序数组中出现 N/2 次以上的数字

> 原文:[https://www . geeksforgeeks . org/find-出现次数超过 n-2 次的 java 排序数组/](https://www.geeksforgeeks.org/find-occurrence-of-number-more-than-n-2-times-in-a-sorted-array-in-java/)

给定一个由 n 个整数组成的排序数组和一个整数 X，任务是找出给定的整数 X 在数组中出现的次数是否超过 n/2 次。

```java
Input: arr[] = {1,1,2,3,3,3,3,3,3,3,3,3,4,5,6,6,7}, x=3
Output: 3 occurs 9 times which is more than 8 times

Input: arr[] = {1,1,2,3,3,3,3,3,3,3,3,3,4,5,6,6,7}, x=6
Output: 6 doesn't occur more than 8 times
```

**方法#1:**

*   维护一个计数变量，用 0 初始化它。
*   迭代数组并将每个元素与 x 进行比较，如果 x 等于 x，则增加计数。
*   迭代整个数组后，检查 count 变量的值是否大于 n/2(数组长度的一半)。
*   如果计数变量的值大于 n/2，则打印“真”或“假”。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to check whether element
// x occurs more then n/2 times or not

class GFG {

    static boolean isOccurMoreThenHalfTimes(int arr[],
                                            int x)
    {
        int len = arr.length;
        // initialize the count by 0
        int count = 0;
        for (int i = 0; i < len; i++) {
            // if x is equal to arr[i],increment the count
            if (arr[i] == x)
                count++;
        }
        // checking the value of count variable
        if (count > len / 2)
            return true;
        else
            return false;
    }
    public static void main(String[] args)
    {
        // driver code
        int arr[] = { 1, 1, 2, 3, 3, 3, 3, 3, 3,
                      3, 3, 3, 4, 5, 6, 6, 7 };
        int x = 3;
        // calling the function and storing
        // the returned result
        boolean answer = isOccurMoreThenHalfTimes(arr, x);
        if (answer) {
            System.out.println("true");
        }
        else {
            System.out.println("false");
        }
    }
}
```

**Output**

```java
true
```

*   **时间复杂度-** 0(N)
*   **空间复杂度:** 0(1)

**接近#2:**

1.  使用下限函数在排序数组中查找下限索引。
2.  使用上限函数在排序数组中查找上限索引。
3.  找出上限和下限指数之间的差异。
4.  如果差异大于 N/2，则打印发生的次数大于 N/2。
5.  否则打印不会超过 N/2 次。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
class Main {
    public static int lower_bound(int arr[], int low,
                                  int high, int X)
    {

        // Base Case
        if (low > high) {
            return low;
        }

        // Find the middle index
        int mid = low + (high - low) / 2;

        // If arr[mid] is greater than
        // or equal to X then search
        // in left subarray
        if (arr[mid] >= X) {
            return lower_bound(arr, low, mid - 1, X);
        }

        // If arr[mid] is less than X
        // then search in right subarray
        return lower_bound(arr, mid + 1, high, X);
    }

    // Recursive implementation of
    // upper_bound
    public static int upper_bound(int arr[], int low,
                                  int high, int X)
    {

        // Base Case
        if (low > high)
            return low;

        // Find the middle index
        int mid = low + (high - low) / 2;

        // If arr[mid] is less than
        // or equal to X search in
        // right subarray
        if (arr[mid] <= X) {
            return upper_bound(arr, mid + 1, high, X);
        }

        // If arr[mid] is greater than X
        // then search in left subarray
        return upper_bound(arr, low, mid - 1, X);
    }

    // Function to implement lower_bound
    // and upper_bound of X
    public static int printBound(int arr[], int N, int X)
    {
        int lower, upper;
        // If lower_bound doesn't exists
        if (arr[0] == X) {
            lower = 0;
        }
        else {

            // Find lower_bound
            lower = lower_bound(arr, 0, N, X);
        }

        // If upper_bound doesn't exists
        if (arr[N - 1] == X) {
            upper = N - 1;
        }
        else {

            // Find upper_bound
            upper = upper_bound(arr, 0, N, X);
        }
        return upper - lower;
    }

    public static void main(String[] args)
    {
        int X = 3;
        int arr[] = { 1, 1, 2, 3, 3, 3, 3, 3, 3,
                      3, 3, 3, 4, 5, 6, 6, 7 };
        int occurrence = printBound(arr, arr.length, X);
        if (occurrence >= arr.length / 2) {
            System.out.println(
                X + " occurs " + occurrence
                + " times which is more than "
                + arr.length / 2 + " times");
        }
        else {
            System.out.println(X
                               + " doesn't occur more than "
                               + arr.length / 2 + " times");
        }
    }
}
```

**Output**

```java
3 occurs 9 times which is more than 8 times
```

**时间复杂度:** O(对数 n)