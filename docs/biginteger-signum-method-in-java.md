# Java 中的大整数 signum()方法

> 原文:[https://www . geesforgeks . org/big integer-signum-method-in-Java/](https://www.geeksforgeeks.org/biginteger-signum-method-in-java/)

**先决条件:** [【大整数基础知识】](https://www.geeksforgeeks.org/biginteger-class-in-java/)
**Java . math . big integer . signum()**方法帮助我们识别大整数是正还是零还是负。它根据以下条件返回以下值之一:

*   当数字为负数时返回-1
*   当数字为零时返回 0
*   当数字为正数时返回+1

**语法:**

```java
public int signum()
```

**参数:**该方法不取任何参数。
**返回值:**当-1、0 或 1 分别为负、零或正时，该方法返回它们作为该大整数的值。

**示例:**

```java
Input: 2300 
Output: 1
Explanation: 2300 is positive number 
so the method returns 1

Input: -5482549 
Output: -1
```

下面的程序说明了 BigInteger 的 signum()方法。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Program Demonstrate signum() method of BigInteger

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {
        // Creating BigInteger object
        BigInteger biginteger = new BigInteger("2300");

        // Call signum() method on bigInteger
        // store the return value as int
        int sigvalue = biginteger.signum();

        // Depending upon sign value find sign of biginteger
        String sign = null;
        if (sigvalue == 0)
            sign = "zero";
        else if (sigvalue == 1)
            sign = "positive";
        else
            sign = "negative";

        // Defining result
        String result = "BigInteger " + biginteger + " is " +
        sign + " and Sing value is " + sigvalue;

        // Print result
        System.out.println(result);
    }
}
```

**Output:** 

```java
BigInteger 2300 is positive and Sing value is 1
```

**参考:**T2【https://docs . Oracle . com/javase/7/docs/API/Java/math/biginteger . html # signum()T4】