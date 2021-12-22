# 用进位乘法生成随机数的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序生成随机数-使用带进位乘法/](https://www.geeksforgeeks.org/java-program-to-generate-random-numbers-using-multiply-with-carry-method/)

在计算机科学中，乘加进位(MWC)是乔治·马萨利亚发明的一种方法，用于根据从两个到几千个随机选择的种子值的初始集合生成随机整数序列。MWC 方法的主要优点是，它调用简单的计算机整数运算，并导致非常快速地生成具有巨大周期的随机数序列，从大约 2 <sup>60</sup> 到 2 <sup>2000000</sup> 不等。

**示例:**

```
Input : Length = 5
Output: 1581 16 1932 1969 1384

Input : Length = 2
Output: 985 3568
```

**使用的公式:**

> **x(n)=(a * x(n-r)+c(n-1)]mod n**
> 
> **c(n) = (a*x(n-r) + c(n-1))/n**
> 
> 哪里，
> 
> 1.  a 是任何乘数，
> 2.  m 是模量，
> 3.  c 是进位，并且
> 4.  r 是种子的初始数量。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to generate a random numbers
// Based on Multiply with carry method
import java.util.Random;
public class Main {

    public static void main(String args[])
    {
        int Maximum_Sequence_Elements = 10;
        Random random = new Random();
        int Base = 2000;
        int Multiplier = random.nextInt(Base);
        int r = 1;
        int[] c = new int[Maximum_Sequence_Elements];
        int[] x = new int[Maximum_Sequence_Elements];
        c[0] = random.nextInt(Multiplier);
        x[0] = random.nextInt(Base);
        System.out.print("The random number sequence is: "
                         + x[0]);

        // generating sequence

        for (int i = 1; i < Maximum_Sequence_Elements;
             i++) {
            x[i]
                = (Multiplier * x[i - r] + c[i - 1]) % Base;
            c[i]
                = (Multiplier * x[i - r] + c[i - 1]) / Base;
            System.out.print(" " + x[i]);
        }
    }
}
```

**Output**

```
The random number sequence is: 508 1021 1549 857 414 1187 1425 1557 1945 1922
```