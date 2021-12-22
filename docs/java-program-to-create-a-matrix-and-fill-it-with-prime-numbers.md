# 创建矩阵并用素数填充矩阵的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-create-matrix-and-fill-it-with-prime-numbers/](https://www.geeksforgeeks.org/java-program-to-create-a-matrix-and-fill-it-with-prime-numbers/)

**质数**是只能被 1 整除的数，本身不能被其他任何数整除。这里的任务是找到素数，并以矩阵的形式存储它们。

```
Example:  

Prime numbers are: 2, 3, 5, 7

Output:
2    3
5    7

Prime numbers : 2, 3, 5, 7, 9, 11, 13, 17, 19

Output:
2    3     5
7    9     11
13    17    19

```

**进场:**

*   首先，应该创建类，并在类内部创建一个方法来检查质数。
*   这种方法将数字作为输入，然后检查它是否是质数。如果它是质数，那么它将返回真，如果不是，那么返回假。
*   现在，主方法将被创建，在主方法内部，Matrix 类的对象被创建，这样 **isPrime()** 方法可以从主方法访问。
*   行数和列数将取自用户，然后使用它，将创建另一个大小为行*列的数组。
*   素数将存储在这个数组中。
*   现在，通过迭代**结果[]** 数组，素数将被存储到**矩阵[]** 数组中。之后结果会被打印出来。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Create a Matrix and Fill
// it with Prime Numbers

import java.util.Scanner;

public class MatrixWithPrimeNumbers {
    // Function to check a number is prime or not
    boolean isPrime(int num)
    {
        int counter = 0;
        for (int i = 1; i <= num; i++) 
        {
            if (num % i == 0)
                counter = counter + 1;
        }

        if (counter == 2)
            return true;
        else
            return false;
    }

    public static void main(String args[])
    {
        // creating object of Matrix With Prime Numbers
        // class
        MatrixWithPrimeNumbers mwp
            = new MatrixWithPrimeNumbers();

        // Enter the number of rows and column.
        int row = 4;
        int col = 4;

        // 2D array for storing prime numbers
        int Matrix[][] = new int[row][col];

        // size of resultant matrix
        int res = row * col;

        // 1D array for storing prime numbers
        int Result[] = new int[res];

        int i = 0, j;
        int k = 1;

        // Calling the method to check prime and
        // then result will be stored into the array
        while (i < res) 
        {
            if (mwp.isPrime(k) == true)
            {
                Result[i] = k;
                i++;
            }
            k++;
        }

        // the result is now stored into the form
        // of matrix (in 2D array)
        int x = 0;
        for (i = 0; i < row; i++) 
        {
            for (j = 0; j < col; j++) 
            {
                Matrix[i][j] = Result[x];
                x++;
            }
        }

        // printing the result in 2D Array.
        System.out.println("The Resultant Matrix is : ");

        for (i = 0; i < row; i++) 
        {
            for (j = 0; j < col; j++) 
            {
                System.out.print(Matrix[i][j] + " ");
            }
            System.out.println();
        }
    }
}
```

**Output**

```
The Resultant Matrix is : 
2 3 5 7 
11 13 17 19 
23 29 31 37 
41 43 47 53 

```