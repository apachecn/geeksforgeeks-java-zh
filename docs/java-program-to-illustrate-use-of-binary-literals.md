# 演示二进制文字用法的 Java 程序

> 原文:[https://www . geeksforgeeks . org/Java-程序解释二进制文字的使用/](https://www.geeksforgeeks.org/java-program-to-illustrate-use-of-binary-literals/)

二进制文字是用 0 和 1(二进制数字)表示的数字。Java 允许您在二进制数字系统中表达整数类型(字节、短整型、整型和长整型)。要指定二进制文字，请将前缀 0b 或 0B 添加到整数值中。所以，我们可以通过给变量赋值来表示程序中的二进制数字，执行程序后这些变量的输出将是十进制数字。

**在 Java 中实现二进制文字:**

我们可以探索在 Java 编程语言中实现和使用二进制文字的方法。第一个和接下来的 Java 程序是一个实现不同类型的二进制文字的例子。如上所述，Java 允许我们表达字节、短、int 和长类型的二进制文字。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate Use of Binary Literals
public class GFG {
    public static void main(String[] args)
    {
        // Byte type Binary Literal
        byte a1 = 0b011;

        // The b can be lower or upper case
        byte a2 = 0B101;
        System.out.println("Binary Literal in Byte----->");
        System.out.println("a1 = " + a1 + ", "
                           + "a2 = " + a2);

        // Short type Binary Literal
        short b1 = 0b101;

        // The b can be lower or upper case
        short b2 = 0B111;
        System.out.println("Binary Literal in Short----->");
        System.out.println("b1 = " + b1 + ", "
                           + "b2 = " + b2);

        // Int type Binary literal
        int c1 = 0b011;

        // The b can be lower or upper case
        int c2 = 0B111;
        System.out.println(
            "Binary Literal in Integer----->");
        System.out.println("c1 = " + c1 + ", "
                           + "c2 = " + c2);

        // Long type Binary literal
        long d1 = 0b0000011111100011;

        // The b can be lower or upper case
        long d2 = 0B0000011111100001;

        System.out.println("Binary Literal in Long----->");
        System.out.println("d1 = " + d1 + ", "
                           + "d2 = " + d2);
    }
}
```

**Output**

```java
Binary Literal in Byte----->
a1 = 3, a2 = 5
Binary Literal in Short----->
b1 = 5, b2 = 7
Binary Literal in Integer----->
c1 = 3, c2 = 7
Binary Literal in Long----->
d1 = 2019, d2 = 2017

```

在 Java 中，可以对二进制文字使用运算符来执行操作。下面的 Java 程序是一个在二进制文本上实现不同的数学和比较操作的例子。对二进制文字进行这些操作的结果是十进制数字。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate Use of Binary Literals
public class GFG {
    public static void main(String[] args)
    {
        byte n1 = 3; // Decimal number
        byte n2 = 0b011; // Binary of 5
        byte n3 = -0b111; // Negative binary number
        byte n4 = 0b1101;

        System.out.println("n1 = " + n1);
        System.out.println("n2 = " + n2);
        System.out.println("n3 = " + n3);
        System.out.println("n4 = " + n4);

        // Checking if the decimal and binary digits are
        // equal
        System.out.println("is n1 and n2 equal: "
                           + (n1 == n2));
        // Adding 1 to a binary digit
        System.out.println("n2 + 1 = " + (n2 + 1));

        // Adding 1 to a negative binary digit
        System.out.println("n3 + 1 = " + (n3 + 1));

        // Multiplying 2 with a binary digit
        System.out.println("n4 x 2 = " + (n4 * 2));
    }
}
```

**Output**

```java
n1 = 3
n2 = 3
n3 = -7
n4 = 13
is n1 and n2 equal: true
n2 + 1 = 4
n3 + 1 = -6
n4 x 2 = 26

```