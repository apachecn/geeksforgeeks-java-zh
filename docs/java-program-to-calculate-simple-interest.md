# 计算单利的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到计算-简单利息/](https://www.geeksforgeeks.org/java-program-to-calculate-simple-interest/)

简单利息是计算贷款利息的一种快速方法。单利是通过每日利率乘以本金再乘以两次付款之间的天数来确定的。

单利公式为:

```
Simple Interest = (P x T x R)/100 
```

***其中，***

*   P is the principal amount.
*   T is time.
*   R is the interest rate

**示例:–**

```
Example 1:

Input :  P = 10000
         R = 5
         T = 5
Output : 2500

Explanation - We need to find simple interest on 
Rs. 10, 000 at the rate of 5% for 5 
units of time.

Example 2:

Input :  P = 3000
         R = 7
         T = 1
Output : 210
```

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to compute
// simple interest for given principal
// amount, time and rate of interest.
import java.io.*;

class GFG {
    public static void main(String args[])
    {
        // We can change values here for
        // different inputs
        float P = 1, R = 1, T = 1;

        /* Calculate simple interest */
        float SI = (P * T * R) / 100;
        System.out.println("Simple interest = " + SI);
    }
}

// This code is contributed by Anant Agarwal.
```

**Output**

```
Simple interest = 0.01
```

**例 2:**

## Java

```
// Java program to compute
// simple interest for given principal
// amount, time and rate of interest.
import java.io.*;

class GFG {
    public static void main(String args[])
    {
        // We can change values here for
        // different inputs
        float P = 10000, R = 5, T = 5;

        // Calculate simple interest
        float SI = (P * T * R) / 100;
        System.out.println("Simple interest = " + SI);
    }
}
```

**输出**

```
Simple interest = 2500.0
```

更多详情请参考[程序上的完整文章寻找简单兴趣](https://www.geeksforgeeks.org/program-find-simple-interest/)！