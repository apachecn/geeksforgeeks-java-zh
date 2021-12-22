# 不使用算术运算符将两个数相加的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-不使用算术运算符的程序加二数/](https://www.geeksforgeeks.org/java-program-to-add-two-numbers-without-using-arithmetic-operator/)

这里，我们需要写一个函数，返回两个指定整数的和。并且该函数不能使用任何算术运算符，如++、++、–、-..等等。).这将是一个非常基本的初级程序，通过简单地使用‘+’运算符计算总和，从而简单地打印和显示结果。但是如果我们不约束不使用任何算术运算符，那么只有一种方法，那就是使用 [*异或*运算符](https://www.geeksforgeeks.org/bitwise-operators-in-c-cpp/)，它可以对两个给定的位执行加法运算。对于进位位**、**我们可以使用*和* ( &)运算符。

使用[位操作符](https://www.geeksforgeeks.org/bitwise-operators-in-java/)完成。这里我们将主要使用以下三种操作:

1.  逐位异或
2.  逐位“与”
3.  逐位左移运算符

首先，数字被转换成二进制格式。考虑整数数据类型的 8 个索引。现在进位由一个逐位左移操作符处理，二进制的其余部分在屏幕上显示为一个整数，表示上述两个整数之和。如下所示:

```java
Input :1, 2
Output : 3
```

```java
a = 1 : 00000001
b = 2 : 00000010
----------------
c = 3 : 00000011 
```

**实施:**

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to find the Sum of Two Numbers
// Without Using any Arithmetic Operator

// Importing input output classes 
import java.io.*;

// Main class
class GFG {

    // Method to sum two integer elements
    static int Sum(int a, int b)
    {

        // Iterating until there is no carry
        while (b != 0) {

            // Using AND operator
            int carry = a & b;

            // Using XOR operator
            a = a ^ b;

            // Shifting the carry by one so that
            // adding it to the integer 'a'
            // gives the desired output
            b = carry << 1;
        }
        return a;
    }

    // Method 2
    // Main driver method
    public static void main(String arg[])
    {

        // Print the sum of custom integer numbers to be
        // summed up passed as an argunts
        System.out.println(Sum(2, 3));
    }
}
```

**Output**

```java
5
```