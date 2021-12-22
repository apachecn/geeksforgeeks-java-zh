# 将数组的偶数&奇数元素存储到单独数组中的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序将数组中的奇偶元素存储到单独的数组中/](https://www.geeksforgeeks.org/java-program-to-store-even-odd-elements-of-an-array-into-separate-arrays/)

给定一个有 N 个数字的数组，用奇数或偶数将这些数字分成两个数组。在最好的情况下，完整的操作需要 O(n)个时间复杂度。为了优化内存使用，首先遍历一个数组，并计算其中偶数和奇数的总数。创建两个数组，数组大小在遍历后计算，并开始存储它们。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Store Even & Odd
// Elements of an Array into Separate Arrays

public class Even_Odd {

    // Print array method
    public static void printArray(int[] array)
    {
        for (int i = 0; i < array.length; i++)
            System.out.print(array[i] + " ");
        System.out.println();
    }
    public static void main(String[] args)
    {
        int n = 8;
        // array with N size
        int array[] = { 23, 55, 54, 9, 76, 66, 2, 91 };

        int evenSize = 0;
        int oddSize = 0;
        for (int i = 0; i < n; i++) {
            if (array[i] % 2 == 0)
                evenSize++;
            else
                oddSize++;
        }
        // odd and even arrays with size
        int[] even = new int[evenSize];
        int[] odd = new int[oddSize];
        // odd and even array iterator
        int j = 0, k = 0;
        for (int i = 0; i < n; i++) {
            if (array[i] % 2 == 0)
                even[j++] = array[i];
            else
                odd[k++] = array[i];
        }
        // print array method
        System.out.print("Even Array contains: ");
        printArray(even);
        System.out.print("Even Array contains: ");
        printArray(odd);
    }
}
```

**Output**

```java
Even Array contains: 54 76 66 2 
Even Array contains: 23 55 9 91 

```

**时间复杂度:** O(n)

**空间复杂度:** O(n)