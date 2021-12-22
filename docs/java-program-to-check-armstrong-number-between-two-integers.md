# 检查两个整数之间阿姆斯特朗数的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-要检查的程序-阿姆斯特朗-两个整数之间的数字/](https://www.geeksforgeeks.org/java-program-to-check-armstrong-number-between-two-integers/)

如果满足以下条件，则具有数字 p、q、r、s…的正整数称为 n 阶阿姆斯特朗数。

```java
pqrs... = pn + qn + rn + sn +....
```

**例:**

```java
370 = 3*3*3 + 7*7*7 + 0 
   =  27 + 343 + 0
   =  370
```

因此，370 是一个*阿姆斯特朗*号。

**示例:**

```java
Input : 100 200
Output :153
Explanation : 100 and 200 are given  
two integers.
 153 = 1*1*1 + 5*5*5 + 3*3*3  
     = 1 + 125 + 27
     =  153
Therefore, only 153 is an Armstrong number between 100 and 200.
```

**进场:**

首先，我们将遍历给定范围内的所有数字。然后，对于每一个数字，我们必须计算其中的位数。如果当前数字中的位数是 n，那么求所述数字中所有数字的(n 次方)的和。如果总和等于当前数字 *i* ，则打印该数字。

**示例:**

## Java

```java
// JAVA program to find Armstrong
// numbers between two integers
import java.io.*;
import java.math.*;

class gfg {

    // Function to print Armstrong
    // Numbers between two integers
    static void ArmstrongNum(int l, int h)
    {
        for (int j = l + 1; j < h; ++j) {

            // Calculating number of digits
            int y = j;
            int N = 0;
            while (y != 0) {
                y /= 10;
                ++N;
            }

            // Calculating the sum of nth
            // power of all the digits
            int sum_power = 0;
            y = j;
            while (y != 0) {
                int d = y % 10;
                sum_power += Math.pow(d, N);
                y /= 10;
            }

            // Checking if the current number
            // i is equal to the sum of nth
            // power of all the digits
            if (sum_power == j)
                System.out.print(j + " ");
        }
    }

    // The Driver code
    public static void main(String args[])
    {
        int n1 = 50;
        int n2 = 500;
        ArmstrongNum(n1, n2);
        System.out.println();
    }
}
```

**输出**

```java
153 370 371 407 

```

同样，我们可以在任何给定的范围内找到阿姆斯特朗数。