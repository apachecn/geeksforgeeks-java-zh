# Java 程序检查阿姆斯特朗号

> 原文:[https://www . geesforgeks . org/Java-要检查的程序-阿姆斯特朗-number/](https://www.geeksforgeeks.org/java-program-to-check-armstrong-number/)

**问题陈述–**给定一个数字 x，编写一个 Java 程序，判断给定的数字是否是阿姆斯特朗的数字。

**示例–**

```
Input : 153
Output : Yes
153 is an Armstrong number.
1*1*1 + 5*5*5 + 3*3*3 = 153

Input : 120
Output : No
120 is not a Armstrong number.
1*1*1 + 2*2*2 + 0*0*0 = 9

Input : 1253
Output : No
1253 is not a Armstrong Number
1*1*1*1 + 2*2*2*2 + 5*5*5*5 + 3*3*3*3 = 723

Input : 1634
Output : Yes
1*1*1*1 + 6*6*6*6 + 3*3*3*3 + 4*4*4*4 = 1634
```

#### **阿姆斯特朗号**

在数学数系中，**阿姆斯特朗数**是任意给定数基中的数，当它的每一位数字都与该数中的总位数相乘时，这个数就是同一个数的总和。简单来说，我们可以说一个正整数的 **n 位数**叫做一个阿姆斯壮数的**阶 n** (阶是一个数中存在的位数的总数)如果，

```
abcd... = pow(a,n) + pow(b,n) + pow(c,n) + pow(d,n) + .... 
```

**比如**，用一个简单的数字 **153** 和十进制，我们看到里面有 3 位数字。如果我们做一个简单的数学运算，把它的每个数字都加到 3 的幂，然后把得到的总和加起来，我们得到 153。

**1<sup>3</sup>+5<sup>3</sup>+3<sup>3</sup>= 153。**153 号是阿姆斯特朗号的一个例子。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to determine whether the number is
// Armstrong number or not
public class Armstrong {
    /* Function to calculate x raised to the
       power y */
    int power(int x, long y)
    {
        if (y == 0)
            return 1;
        if (y % 2 == 0)
            return power(x, y / 2) * power(x, y / 2);
        return x * power(x, y / 2) * power(x, y / 2);
    }

    /* Function to calculate order of the number */
    int order(int x)
    {
        int n = 0;
        while (x != 0) {
            n++;
            x = x / 10;
        }
        return n;
    }

    // Function to check whether the given number is
    // Armstrong number or not
    boolean isArmstrong(int x)
    {
        // Calling order function
        int n = order(x);
        int temp = x, sum = 0;
        while (temp != 0) {
            int r = temp % 10;
            sum = sum + power(r, n);
            temp = temp / 10;
        }

        // If satisfies Armstrong condition
        return (sum == x);
    }

    // Driver Program
    public static void main(String[] args)
    {
        Armstrong ob = new Armstrong();
        int x = 153;
        System.out.println(x + " : " + ob.isArmstrong(x));
        x = 1253;
        System.out.println(x + " : " + ob.isArmstrong(x));
    }
}
```

**Output**

```
153 : true
1253 : false
```