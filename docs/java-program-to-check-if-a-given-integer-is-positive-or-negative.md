# 检查给定整数是正还是负的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序检查给定整数是正数还是负数/](https://www.geeksforgeeks.org/java-program-to-check-if-a-given-integer-is-positive-or-negative/)

这里的任务是检查给定的整数是正数还是负数。下面是一个数的一些基本性质。

*   If the integer is greater than zero, it is a positive integer.
*   If the number is less than zero, it is a negative integer.
*   If the number is equal to zero, it is neither negative nor positive.

```java
Input: X = 12
Output: Positive
Explanation: Value of X is greater than 0 so it is Positive.

Input: x = -5
Output: Negative
Explanation: Value of X less than 0 so it is negative.
```

**方法 1:使用关系运算符，我们可以检查一个整数是正数还是负数。**

*   If the number > is 0, the number is positive.
*   If the number < is 0, the number is negative.
*   If a number is neither positive nor negative, it is equal to 0.

下面是上述方法的 java 实现:

## Java

```java
// Java Program to Check if a Given Integer
// is Positive or Negative

import java.io.*;

class GFG {

    // Function to check positive and negative
    static String checkPosNeg(int x)
    {

        // checks the number is greater than 0 or not
        if (x > 0)
            return "Positive";

        else if (x < 0)
            return "Negative";

        else
            return "zero";
    }

    // Driver Function
    public static void main(String[] args)
    {
        // number to be check
        int firstNumber = 912;
        System.out.println(firstNumber + " is "
                           + checkPosNeg(firstNumber));
    }
}
```

输出

```java
912 is Positive
```