# Java 程序反转一个数字&检查它是否是回文

> 原文:[https://www . geesforgeks . org/Java-program-to-reverse-a-number-check-if-it-a-回文/](https://www.geeksforgeeks.org/java-program-to-reverse-a-number-check-if-it-is-a-palindrome/)

如果给定数的反序与给定数的反序相同，则给定数本质上可以称为回文。数字的长度是 log <sub>10</sub> (n)，也就是说，对于使用字符串操作(如创建反转和检查回文)的大整数，需要 log <sub>10</sub> (n)的时间。

【under Java int 限制下的数字

**示例:**

```java
Input : n = 46355364
Output: Reverse of n = 46355364
    Palindrome = Yes

Input : n = 87476572465
Output: Reverse of n = 56427567478
    Palindrome = No

```

我们可以用多种方式反转一个数字，下面是同样的迭代实现。

**迭代算法:**

```java
Input:  number
1\. Initialize reversed_number = 0
2\. Loop while num
ber > 0
     a. Multiply reversed_number by 10 and add number  % 10 to reversed_number
               reversed_number  = reversed_number*10 + number %10;
     b. Divide number by 10
3\. Return reversed_number

```

**示例:**

```java
number = 1234
reversed_number= 0

reversed_number = reversed_number *10 + number%10 = 4
number = number/10 = 123

reversed_number = reversed_number*10 + number%10 = 20 + 6 = 43
number = number/10 = 12

reversed_number = reversed_number*10 + number%10 = 260 + 5 = 432
number = number/10 = 1

reversed_number = reversed_number*10 + number%10 = 265 + 4 = 4321
number = number/10 = 0

```

下面是上述方法的实现。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to reverse a number
// and find if it is a palindrome or not
class GFG {

    // Iterative function to
    // reverse the digits of number
    static int reversNumber(int n)
    {
        int reversed_n = 0;
        while (n > 0) {
            reversed_n = reversed_n * 10 + n % 10;
            n = n / 10;
        }
        return reversed_n;
    }

    // Main function
    public static void main(String[] args)
    {
        int n = 123464321;
        int reverseN = reversNumber(n);
        System.out.println("Reverse of n = " + reverseN);

        // Checking if n is same
        // as reverse of n
        if (n == reverseN)
            System.out.println("Palindrome = Yes");
        else
            System.out.println("Palindrome = No");
    }
}
```

**Output**

```java
Reverse of n = 123464321
Palindrome = Yes

```

**时间复杂度:** O(log <sub>10</sub> (n))其中 n 为输入数。

**B .大整数:使用大整数类**

**例**

```java
Input : n = 12345678999999999987654321
Output: Reverse of n = 12345678999999999987654321
    Palindrome = Yes

```

**接近**

1.  接受 BigInteger 变量的输入。
2.  使用反转方法反转给定的 BigInteger。
3.  使用 compareTo()方法比较两个大整数。

下面是上述方法的实现。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to reverse a number
// and find if it is a palindrome or not
import java.io.*;
import java.math.BigInteger;
class GFG {
    // Reverse Big Integer
    public static BigInteger reverse(BigInteger n)
    {
        String s = n.toString();
        StringBuilder sb = new StringBuilder(s);
        return new BigInteger(sb.reverse().toString());
    }
    // Main Function
    public static void main(String[] args)
    {
        BigInteger n
            = new BigInteger("12345678999999999987654321");
        BigInteger reverseN = reverse(n);
        System.out.println("Reverse of n = " + reverseN);

        // Checking if n is same
        // as reverse of n
        if (n.compareTo(reverseN) == 0)
            System.out.println("Palindrome = Yes");
        else
            System.out.println("Palindrome = No");
    }
}
```

**Output**

```java
Reverse of n = 12345678999999999987654321
Palindrome = Yes

```

**时间复杂度:** O(log <sub>10</sub> (n))其中 n 为输入数。