# 不使用数学幂()方法计算 Java 中一个数的幂

> 原文:[https://www . geesforgeks . org/不使用数学幂法计算 java 中数字的幂/](https://www.geeksforgeeks.org/calculating-the-power-of-a-number-in-java-without-using-math-pow-method/)

我们需要在不使用预定义函数 java.lang.Math.pow()的情况下计算一个数的幂

在 Java 中，我们可以通过:

1.  Calculate the power of a number through the while loop or the for loop.

要计算任何数的幂，需要基数和指数。

**先决条件:**

对 Java 算术运算符、数据类型、基本输入/输出和循环等的基本理解。

**例:**

```java
Input : base = 3, exponent = 3
Output: 27

Input : base = 2, exponent = 4
Output: 16
```

**实施:**

**1。使用 while 循环:**基础值和功率值被分配了各自的值。现在，while 循环将继续将结果变量乘以基变量，直到幂变为零。

下面是使用 while 循环的问题语句的实现:

## Java

```java
// Calculate the power of a number in Java using while loop
import java.io.*;

public class JavaApplication1 {
    public static void main(String[] args)
    {
        int base = 3, power = 3;
        int result = 1;
        // running loop while the power > 0
        while (power != 0) {
            result = result * base;
            // power will get reduced after
            // each multiplication
            power--;
        }
        System.out.println("Result =  " + result);
    }
}
```

**输出**

```java
Result =  27

```

**时间复杂度:** O(N)，其中 N 为幂。

**2。用于循环:**基础值和功率值已分配给各自的值。现在，在上面的程序中，我们可以使用 for 循环代替 while 循环。

下面是使用 while 循环的问题语句的实现:

## Java

```java
// Calculate the power of a number in Java using for loop
import java.io.*;

public class JavaApplication1 {
    public static void main(String[] args)
    {
        int base = 3, power = 3;
        int result = 1;

        for (power = 3; power != 0; power--) {
            result = result * base;
        }
        System.out.println("Result =  " + result);
    }
}
```

**输出**

```java
Result =  27

```

**时间复杂度:** O(N)，其中 N 为幂。

**3。使用** **分治法:**上述操作只需计算一次幂(基数，指数/2)并存储，即可优化为 0(对数 N)。

## Java

```java
// Calculate the power of a number
// in Java using Divide and Conquer
class GFG {

    public static int power(int x, int y)
    {
        int temp;
        if (y == 0)
            return 1;
        temp = power(x, y / 2);

        if (y % 2 == 0)
            return temp * temp;
        else {
            if (y > 0)
                return x * temp * temp;
            else
                return (temp * temp) / x;
        }
    }

    // Driver code
    public static void main(String[] args)
    {
        int x = 2;
        int y = 3;
        System.out.println(power(x, y));
    }
}
```

**输出**

```java
8

```

**时间复杂度:** O(log N)，其中 N 为幂。