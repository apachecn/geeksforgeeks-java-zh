# 显示数字和前 N 个自然数之和的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序-显示-数字-和-第一个-n-自然数的和/](https://www.geeksforgeeks.org/java-program-to-display-numbers-and-sum-of-first-n-natural-numbers/)

使用迭代方法打印前 N 个自然数，即使用 for 循环。For 循环有三个参数初始化、测试条件和递增/递减。

```java
Input:     N = 10
Output:    First 10 Numbers = 1, 2, 3, 4, 5, 6, 7, 8, 9, 10
           Sum of first 10 Natural Number = 55

Input:     N = 5
Output:    First 5 Numbers = 1, 2, 3, 4, 5
           Sum of first 5 Natural Number = 15

```

**接近**

1.  i = 1 时开始循环初始化。
2.  将测试条件写成 i <= N。
3.  将 increment 语句作为 i++或 i+=1 添加。
4.  用 0 初始化变量和。
5.  在 for 循环的每次迭代中，用和开始添加 I，并打印 I。
6.  在循环结束时打印总和。

下面是上述方法的实现

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Display Numbers
// from 1 to N Using For Loop and
// sum of First N Natural Number
import java.io.*;
class GFG {
    public static void main(String[] args)
    {
        int N = 10;
        int sum = 0;
        System.out.print("First " + N + " Numbers = ");

        // we initialize the value of the variable i 
        // with 1 and increment each time with 1
        for (int i = 1; i <= N; i++) {

            // print the value of the variable as
            // long as the code executes
            System.out.print(i + " ");
            sum += i;
        }
        System.out.println();
        System.out.println("Sum of first " + N
                           + " Natural Number = " + sum);
    }
}
```

**Output**

```java
First 10 Numbers = 1 2 3 4 5 6 7 8 9 10 
Sum of first 10 Natural Number = 55
```