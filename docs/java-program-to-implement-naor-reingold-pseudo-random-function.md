# 实现 Naor-Reingold 伪随机函数的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-naor-rein gold-伪随机-函数/](https://www.geeksforgeeks.org/java-program-to-implement-naor-reingold-pseudo-random-function/)

Naor-Reingold 伪随机函数是一个生成随机数的函数。Moni Naor 和 Omer Reingold 描述了私钥和公钥密码中各种加密原语的有效构造。

**示例:**

```java
Input : N = 5
Output: 9.0, 9.0, 3.0, 9.0, 3.0

Input : N = 7
Output: 9.0, 81.0, 9.0, 9.0, 3.0, 3.0, 9.0
```

**算法:**

*   声明变量 p，l，g，n，x 和数组 a[]和 arr[]
*   从用户那里获取生成随机数的输入
*   生成随机数并使用定义的方法:

```java
Let p and l be prime numbers with l|p−1.
Select an element g ε Fp* of multiplicative order l. 
Then for each n-dimensional vector a = (a0,a1, ..., an).

They define the function as:
fa(x)=ga0.a1x1a2x2…..anxn ε Fp
```

*   打印随机数

以下是脑-金伪随机函数的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Implement Naor-Reingold
// Pseudo Random Function
import java.util.*;
public class Main {
    public static void randomNumbers()
    {
        // Creating arrays and defining variables
        int p = 7, l = 2, g = 3, n = 6, x;

        int a[] = { 1, 2, 2, 1 };

        int arr[] = new int[4];

        Random random = new Random();

        int num = 10;
        System.out.println("The Random numbers are: ");

        // Generating Random Numbers using
        // Naor-Reingold Pseudo Random Function approach
        for (int i = 0; i < num; i++) {
            x = random.nextInt(num) % 16;

            for (int j = 3; j >= 0; j--) {
                arr[j] = x % 2;
                x /= 2;
            }
            int mult = 1;

            for (int k = 0; k < 4; k++) {
                mult *= Math.pow(a[k], arr[k]);
            }
            System.out.print(Math.pow(g, mult) + ", ");
        }
    }
    public static void main(String args[])
    {
        randomNumbers();
    }
}
```

**Output**

```java
The Random numbers are: 
9.0, 9.0, 3.0, 81.0, 3.0, 81.0, 9.0, 9.0, 3.0, 3.0, 
```