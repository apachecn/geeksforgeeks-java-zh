# 检查一个号码是否是间谍号码的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-check-a-number-is-spy-number-or-not/](https://www.geeksforgeeks.org/java-program-to-check-if-a-number-is-spy-number-or-not/)

如果所有数字的总和等于所有数字的乘积，则称一个数字为间谍号。为了执行任务，我们需要反转数字，这将花费 log(N)时间。

**例:**

```java
Input : 22
Output: Given number is a SPY number.
Explanation: Sum of the number is 4 (2 + 2)
             Product of the number is as 4 (2 * 2) 
Input : 1241
Output:  Given number is not a SPY number.
```

**方法:**

1.  Calculate the sum of the digits of the input number.
2.  Calculate the digit product of the input number.
3.  If the sum of digits is equal to the product of digits, the number is a spy number, otherwise it is a non-spy number.

下面是上述方法的实现:

T3】JavaT5

```java
// Java Program to Check If a Number is Spy number or not
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        int product = 1, sum = 0, ld;
        int n = 22;

        // calculate sum and product of the number here.
        while (n > 0) {
            ld = n % 10;
            sum = sum + ld;
            product = product * ld;
            n = n / 10;
        }

        // compare the sum and product.
        if (sum == product)
            System.out.println(
                "Given number is spy number");
        else
            System.out.println(
                "Given number is not spy number");
    }
}
```

T6T8**输出**T1

**复杂度:O(log(n))**