# 使用 Java 的基本计算器程序

> 原文:[https://www . geesforgeks . org/basic-calculator-program-use-Java/](https://www.geeksforgeeks.org/basic-calculator-program-using-java/)

创建一个简单的计算器，它可以根据用户输入执行基本的算术运算，如加法、减法、乘法或除法。

**示例:**

> 输入数字:
> 
> Two
> 
> Two
> 
> 输入运算符(+、-、*、/)
> 
> +
> 
> 最终结果:
> 
> 2.0 + 2.0 = 4.0

**采用的方法:**

*   使用[扫描仪](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/scanner-class-in-java/&sa=U&ved=2ahUKEwiinq7g7YbtAhX9xzgGHR1KAPwQFjAAegQIBhAC&usg=AOvVaw3q2pSLH7JpC2tHq3kSn-6S)类获取两个数字。开关情况分支用于执行特定的部分。
*   使用[开关盒](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/switch-statement-in-java/&sa=U&ved=2ahUKEwi24pjL7YbtAhUIzDgGHYrSD4UQFjAAegQIBBAC&usg=AOvVaw15q_1uIqbev-aSMqLlDk7D)评估各自的操作。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program for simple calculator

import java.io.*;
import java.lang.*;
import java.lang.Math;
import java.util.Scanner;
public class BasicCalculator {

    public static void main(String[] args)
    {
        // stores two numbers
        double num1, num2;

        // Take input from the user
        Scanner sc = new Scanner(System.in);

        System.out.println("Enter the numbers");

        // take the inputs
        num1 = sc.nextDouble();

        num2 = sc.nextDouble();

        System.out.println("Enter the operator (+,-,*,/)");

        char op = sc.next().charAt(0);

        double o = 0;

        switch (op) {

        // case to add two numbers
        case '+':

            o = num1 + num2;

            break;

        // case to subtract two numbers
        case '-':

            o = num1 - num2;

            break;

        // case to multiply two numbers
        case '*':

            o = num1 * num2;

            break;

        // case to divide two numbers
        case '/':

            o = num1 / num2;

            break;

        default:

            System.out.println("You enter wrong input");

            break;
        }

        System.out.println("The final result:");

        System.out.println();

        // print the final result
        System.out.println(num1 + " " + op + " " + num2
                           + " = " + o);
    }
}
```

**输出:**

> 输入数字:
> 
> Two
> 
> Two
> 
> 输入运算符(+、-、*、/)
> 
> +
> 
> 最终结果:
> 
> 2.0 + 2.0 = 4.0

**时间复杂度:** O(1)

**辅助空间:** O(1)