# 寻找前 N 个奇数之和的 Java 程序&偶数

> 原文:[https://www . geesforgeks . org/Java-program-to-find-first-n-奇数-偶数之和/](https://www.geeksforgeeks.org/java-program-to-find-the-sum-of-first-n-odd-even-numbers/)

当任何以 0，2，4，6，8 结尾的数被 2 除时，就是偶数。而当任何一个数以 1，3，5，7，9 结尾时，不除以 2 就是奇数。

**示例:**

```
Input : 8
Output: Sum of First 8 Even numbers = 72
        Sum of First 8 Odd numbers = 64

```

**方法#1:迭代**

1.  创建两个变量 evenSum 和 oddSum，并用 0 初始化它们。
2.  从 1 到 2*n 的循环开始
3.  如果我是偶数，就用偶数加 1。
4.  否则用 oddSum 加 I。
5.  在循环结束时打印偶数和奇数。

下面是 Java 程序的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Calculate the Sum of First N Odd & Even Numbers in Java
import java.io.*;

public class GFG {

    // Driver function
    public static void main(String[] args)
    {
        int n = 8;
        int evenSum = 0;
        int oddSum = 0;

        for (int i = 1; i <= 2 * n; i++) {
            // check even & odd using Bitwise AND operator
            if ((i & 1) == 0)
                evenSum += i;
            else
                oddSum += i;
        }
        // Sum of even numbers less then 17
        System.out.println("Sum of First " + n
                           + " Even numbers = " + evenSum);

        // sum of odd numbers less then 17
        System.out.println("Sum of First " + n
                           + " Odd numbers = " + oddSum);
    }
}
```

**Output**

```
Sum of First 8 Even numbers = 72
Sum of First 8 Odd numbers = 64

```

**时间复杂度:** O(N)，其中 N 为前 N 个偶数/奇数的个数。

**方法二:使用 AP 公式。**

*   前 N 个偶数之和= n * (n+1)
*   前 N 个奇数之和= n * n

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Calculate the Sum of First N Odd & Even Numbers in Java
import java.io.*;

public class GFG {

    // Function to find the sum of even numbers
    static int sumOfEvenNums(int n) { return n * (n + 1); }

    // Function to find the sum of odd numbers.
    static int sumOfOddNums(int n) { return n * n; }

    // Driver function
    public static void main(String[] args)
    {
        int n = 10;
        int evenSum = sumOfEvenNums(n);
        int oddSum = sumOfOddNums(n);

        // Sum of even numbers
        System.out.println("Sum of First " + n
                           + " Even numbers = " + evenSum);

        // sum of odd numbers
        System.out.println("Sum of First " + n
                           + " Odd numbers = " + oddSum);
    }
}
```

**Output**

```
Sum of First 10 Even numbers = 110
Sum of First 10 Odd numbers = 100

```

**时间复杂度:** O(1)