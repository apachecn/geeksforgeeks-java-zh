# Java 中的 BigInteger 余数()方法

> 原文:[https://www . geesforgeks . org/big integer-余数法 in-java/](https://www.geeksforgeeks.org/biginteger-remainder-method-in-java/)

**java.math.BigInteger .余数(BigInteger big)** 方法返回一个 BigInteger，其值等于(此 BigInteger % big(BigInteger 作为参数传递))。余数运算在这个大整数被作为参数传递的另一个大整数除之后找到余数。

**语法:**

```java
public BigInteger remainder(BigInteger big)
```

**参数:**该函数接受单个强制参数 **big** ，它指定了我们想要用来划分这个 BigInteger 对象的 bigInteger 对象。

**返回:**该方法返回的 BigInteger 等于这个 BigInteger 的% big(BigInteger 作为参数传递)。

**异常**该方法抛出一个*算法异常*–当*大= 0 时*

**示例:**

```java
Input: BigInteger1=321456, BigInteger2=31711
Output: 4346
Explanation: BigInteger1.remainder(BigInteger2)=4346\. The divide operation 
between 321456 and 31711 returns 4346 as remainder.

Input: BigInteger1=59185482345, BigInteger2=59185482345
Output: 0
Explanation: BigInteger1.remainder(BigInteger2)=0\. The divide operation between 
59185482345 and 59185482345 returns 0 as remainder.

```

**示例 1:下面的程序说明了 BigInteger 类**的余数()方法

```java
// Java program to demonstrate remainder() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {

        // Creating 2 BigInteger objects
        BigInteger b1, b2;

        b1 = new BigInteger("321456");
        b2 = new BigInteger("31711");

        // apply remainder() method
        BigInteger result = b1.remainder(b2);

        // print result
        System.out.println("Result of remainder "
                           + "operation between " + b1
                           + " and " + b2 + " equal to " + result);
    }
}
```

**Output:**

```java
Result of remainder operation between 321456 and 31711 equal to 4346

```

**例 2:两者值相等时。**

```java
// Java program to demonstrate remainder() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {

        // Creating 2 BigInteger objects
        BigInteger b1, b2;

        b1 = new BigInteger("3515219485");
        b2 = new BigInteger("3515219485");

        // apply remainder() method
        BigInteger result = b1.remainder(b2);

        // print result
        System.out.println("Result of remainder "
                           + "operation between " + b1
                           + " and " + b2 + " equal to " + result);
    }
}
```

**Output:**

```java
Result of remainder operation between 3515219485 and 3515219485 equal to 0

```

**示例 3:当作为参数传递的 BigInteger 等于零时，程序显示异常。**

```java
// Java program to demonstrate remainder() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {

        // Creating 2 BigInteger objects
        BigInteger b1, b2;

        b1 = new BigInteger("3515219485");
        b2 = new BigInteger("0");

        // apply remainder() method
        BigInteger result = b1.remainder(b2);

        // print result
        System.out.println("Result of remainder "+
                "operation between " + b1
                + " and " + b2 +
                " equal to " + result);
    }
}
```

```java
Output:
Exception in thread "main" java.lang.ArithmeticException: BigInteger divide by zero
    at java.math.MutableBigInteger.divideKnuth(MutableBigInteger.java:1179)
    at java.math.MutableBigInteger.divideKnuth(MutableBigInteger.java:1163)
    at java.math.BigInteger.remainderKnuth(BigInteger.java:2167)
    at java.math.BigInteger.remainder(BigInteger.java:2155)
    at GFG.main(GFG.java:16)

```

**参考:**
[大整数余数()单据](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#remainder(java.math.BigInteger))