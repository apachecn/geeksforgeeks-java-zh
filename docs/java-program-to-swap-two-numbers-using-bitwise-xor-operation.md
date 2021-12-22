# 使用按位异或运算交换两个数字的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到交换两个数字-使用按位异或运算/](https://www.geeksforgeeks.org/java-program-to-swap-two-numbers-using-bitwise-xor-operation/)

给定两个数字 x 和 y，我们必须编写一个 Java 程序，使用[逐位异或](https://www.geeksforgeeks.org/tag/xor/)运算来交换两个数字的内容。

```
Input 1: x = 5, y = 10
Output : x = 10, y = 5
Explaination :
1\. x = x ^ y -> x = 15
2\. y = x ^ y -> y = 5
3\. x = x ^ y -> x = 10

Input 2: x = 15, y = 20
Output : x = 20, y = 15

```

按位 XOR 运算符(由^表示)比较两个操作数的相应位，如果它们相等，则返回 1，如果它们不相等，则返回 0。假设我们有两个数字 x 和 y，那么实际上 x^y 会做的是，它会比较 x 和 y 的每个对应位，如果它们不同，它会生成 1 作为考虑的两个位(x 的一个和 y 的一个)的输出，如果位相同，那么它会生成 0 作为两个位的输出。

下面是上述方法的代码实现:-

## Java

```
// Java program to swap the elements using XOR Operator
import java.io.*;
class GFG {
    public static void main(String[] args)
    {
        int x = 5, y = 10;
        // binary equivalent of 5 is 0101
        // binary equivalent of 10 is 1010

        // binary equivalent of x  will become 1111 ie x=15
        x = x ^ y;
        // binary equivalent of y  will become 0101 ie y=5
        y = x ^ y;
        // binary equivalent of x  will become 1010 ie x=10
        x = x ^ y;
        System.out.println("The value of x is " + x
                           + " and the value of y is " + y);
    }
}
```

**输出**

```
The value of x is 10 and the value of y is 5

```