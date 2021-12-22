# 寻找菱形区域的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序查找菱形区域/](https://www.geeksforgeeks.org/java-program-to-find-the-area-of-rhombus/)

菱形是四边长度相等的四边形，菱形也称为等边四边形。

菱形面积的计算公式如下:

> (对角线长度的乘积)/2

**示例:**

```java
Input : p = 2, q = 3
Output: 3

Input : p = 4, q = 5
Output: 10
```

**实现:**

T5】Java

```java
// Java Program to Find the Area of Rhombus
public class AreaOfRhombus {
    public static void main(String[] args)
    {
        double d1, d2;
        // Diagonal 1
        d1 = 2;
        // Diagonal 2
        d2 = 3;
        if (d1 <= 0 || d2 <= 0)
            System.out.println("Length should be positive");
        else
            System.out.println("Area of rhombus = "
                               + (d1 * d2) / 2);
    }
}
```

**输出**

```java
Area of rhombus = 3.0
```