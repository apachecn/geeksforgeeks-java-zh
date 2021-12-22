# 两个浮点数相乘的 Java 程序

> 原文:[https://www . geeksforgeeks . org/Java-程序乘二浮点数/](https://www.geeksforgeeks.org/java-program-to-multiply-two-floating-point-numbers/)

float [类](https://www.geeksforgeeks.org/java-lang-float-class-in-java/) 是一个用于原语类型 float 的包装类，它包含几个方法来有效地处理 float 值，比如将其转换为字符串表示，反之亦然。浮点类的一个对象可以保存一个浮点值。

任务是用 Java 将两个**浮点数**相乘并打印它们的乘积。

**方法:**

*   Initialize two floating-point numbers.
*   Store their multiplication results in a floating-point variable.
*   Print results

## Java

```java
// Java Program to print Multiplication of two floating
// point Number.

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        // f is to ensures that numbers are float DATA TYPE
        float f1 = 1.5f;
        float f2 = 2.0f;

        // to store the multiplied value
        float p = f1 * f2;

        // to print the product
        System.out.println("The product is: " + p);
    }
}
```

**输出**

```java
The product is: 3.0
```