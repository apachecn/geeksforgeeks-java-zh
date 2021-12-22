# 使用类型转换计算两个字节值之和的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序计算两字节值之和-使用类型转换/](https://www.geeksforgeeks.org/java-program-to-calculate-sum-of-two-byte-values-using-type-casting/)

java 中两字节值的加法与普通整数加法相同。字节数据类型是 8 位带符号二进制补码整数。它的最小值为-128，最大值为 127(含)。两字节值的和可能超过给定的字节限制，这种情况可以通过将两字节数的和存储在一个整数变量中来处理。

**例:**

```
Input:  firstByte = 10, secondByte = 23
Output: Sum = 33

Input:  firstByte = 10, secondByte = 23
Output: Sum = 33

```

**类型转换:**类型转换就是将一种数据类型转换成另一种数据类型。例如，在这个程序中，字节值被转换成一个整数。

**方法:**

*   And declare to initialize double-byte variables.
*   Declare an integer variable.
*   Stores the sum of two bytes in an int variable.

下面是上述方法的实现

T3】JavaT5

```
// Java Program to Calculate Sum of
// Two Byte Values Using Type Casting

public class GFG {
    public static void main(String[] args)
    {
        // create two variable of byte type
        byte firstByte = 113;
        byte secondByte = 123;

        // create int variable to store result
        int sum;

        sum = firstByte + secondByte;
        System.out.println("sum = " + sum);
    }
}
```

T6T8**输出**T1