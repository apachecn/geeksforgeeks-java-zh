# 打印数组中第 kth 个元素的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-print-the-kth-element-in-array/](https://www.geeksforgeeks.org/java-program-to-print-the-kth-element-in-the-array/)

我们需要打印给定数组中第 k 个位置的元素。因此，我们通过从用户那里获取关于数组大小的输入，然后获取该数组的所有元素来启动程序。现在，通过输入要从数组中打印元素的位置 k，程序将在数组中的 **k-1** 位置打印元素。

**注**:Java 数组中元素的索引总是从 0 开始，一直延续到数组大小以下的数字 1。因此，对于具有 10 个元素的数组，索引将从 0 到 9。

**示例**

```
Input: 5 (size of an array)
       1, 2, 3, 4, 5 (array elements)
       3 (position k)
Output: 3

Input: 5
       5, 3, 7, 1, 9
       3
Output: 7
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Print the kth Element in the Array

import java.io.*;
import java.util.Scanner;

class GFG {
    public static void main(String[] args)
    {
        {
            int n;

            // scanner object to acces user input
            Scanner s = new Scanner(System.in);
            System.out.print(
                "Enter number of elements you want in array:");

            // storing input in variable
            n = s.nextInt();

            // create int array
            int a[] = new int[n];
            System.out.println("Enter all the elements:");

            // iterating for loop to enter the values in the
            // array
            for (int i = 0; i < n; i++) {
                a[i] = s.nextInt();
            }

            System.out.print(
                "Enter the k th position at which you want to check number:");
            int k = s.nextInt();
            System.out.println("Number is :" + a[k - 1]);
        }
    }
}
```

**输出**

```
Enter number of elements you want in array: 5
Enter all the elements: 
5
3
7
1
9
Enter the k th position at which you want to check number: 3
Number is : 7
```