# 使用包装类

计算 2 的幂的模数除法

> 原文:[https://www . geesforgeks . org/compute-module-division-power-2-number-use-wrapper-class/](https://www.geeksforgeeks.org/compute-modulus-division-power-2-number-using-wrapper-class/)

**先决条件:** [用 2 的幂计算模数除法](https://www.geeksforgeeks.org/compute-modulus-division-by-a-power-of-2-number/)

如你所知，为了得到 n 模 2 <sup>k</sup> ，我们只需要在 n 的二进制表示中返回 k 位(从 LSB 开始)，在 Java 中，你可以使用 [Wrapper 类](https://www.geeksforgeeks.org/wrapper-classes-java/) *toBinaryString()* 方法得到一个数字的二进制字符串表示，并从(str.length()-k)开始获取子字符串。然后通过使用[*integer . parsent()*](https://www.geeksforgeeks.org/string-to-integer-in-java-parseint/)，可以将这个二进制子串转换成余数。下面是演示相同的 Java 程序。

```java
// Java program to Compute modulus
// division by a power-of-2-number

class Test
{
    // Driver method
    public static void main(String[] args) 
    {
        int num = 15;

        int two_power1 = 1;
        int two_power2 = 2;
        int two_power3 = 3;

        String binary = Integer.toBinaryString(num);
        int len = binary.length();

        String rem1 = binary.substring(len-two_power1);
        String rem2 = binary.substring(len-two_power2);
        String rem3 = binary.substring(len-two_power3);

        int reme1 = Integer.parseInt(rem1, 2);
        int reme2 = Integer.parseInt(rem2, 2);
        int reme3 = Integer.parseInt(rem3, 2);

        System.out.println(num + "%" + "2^(" + two_power1 + ") = " + reme1);
        System.out.println(num + "%" + "2^(" + two_power2 + ") = " + reme2);
        System.out.println(num + "%" + "2^(" + two_power3 + ") = " + reme3);
    }
}
```

输出:

```java
15%2^(1) = 1
15%2^(2) = 3
15%2^(3) = 7

```

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。