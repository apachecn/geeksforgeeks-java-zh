# Java 嵌套循环示例

> 原文:[https://www . geesforgeks . org/Java-嵌套循环-带示例/](https://www.geeksforgeeks.org/java-nested-loops-with-examples/)

**嵌套循环**是指另一个循环语句中的一个[循环语句](https://www.geeksforgeeks.org/loops-in-java/)。这就是为什么嵌套循环也被称为“循环内循环”。
**嵌套 for 循环的语法:**

```java
for ( initialization; condition; increment ) {

   for ( initialization; condition; increment ) {

      // statement of inside loop
   }

   // statement of outer loop
}
```

**嵌套 While 循环的语法:**

```java
while(condition) {

   while(condition) {

      // statement of inside loop
   }

   // statement of outer loop
}
```

**嵌套边做边循环的语法:**

```java
do{

   do{

      // statement of inside loop
   }while(condition);

   // statement of outer loop
}while(condition);
```

> **注意:**没有规定循环必须嵌套在自己的类型中。事实上，可以有任何类型的循环嵌套在任何类型和任何级别。

**语法:**

```java
do{

   while(condition) {

      for ( initialization; condition; increment ) {

         // statement of inside for loop
      }

      // statement of inside while loop
   }

   // statement of outer do-while loop
}while(condition);
```

下面是一些示例来演示嵌套循环的使用:
**示例 1:** 下面的程序使用嵌套 for 循环来打印 2D 矩阵。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to print the elements of
// a 2 D array or matrix

import java.io.*;

class GFG {

    public static void print2D(int mat[][])
    {
        // Loop through all rows
        for (int i = 0; i < mat.length; i++) {

            // Loop through all elements of current row
            for (int j = 0; j < mat[i].length; j++)
                System.out.print(mat[i][j] + " ");

            System.out.println();
        }
    }

    public static void main(String args[]) throws IOException
    {
        int mat[][] = { { 1, 2, 3, 4 },
                        { 5, 6, 7, 8 },
                        { 9, 10, 11, 12 } };
        print2D(mat);
    }
}
```

**Output:** 

```java
1 2 3 4 
5 6 7 8 
9 10 11 12
```

**示例 2:** 下面的程序使用嵌套 for 循环打印一个数的所有质因数。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to print all prime factors

import java.io.*;
import java.lang.Math;

class GFG {
    // A function to print all prime factors
    // of a given number n
    public static void primeFactors(int n)
    {
        // Print the number of 2s that divide n
        while (n % 2 == 0) {
            System.out.print(2 + " ");
            n /= 2;
        }

        // n must be odd at this point. So we can
        // skip one element (Note i = i +2)
        for (int i = 3; i <= Math.sqrt(n); i += 2) {
            // While i divides n, print i and divide n
            while (n % i == 0) {
                System.out.print(i + " ");
                n /= i;
            }
        }

        // This condition is to handle the case when
        // n is a prime number greater than 2
        if (n > 2)
            System.out.print(n);
    }

    public static void main(String[] args)
    {
        int n = 315;
        primeFactors(n);
    }
}
```

**Output:** 

```java
3 3 5 7
```