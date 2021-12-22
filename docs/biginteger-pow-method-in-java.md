# Java 中的 BigInteger pow()方法

> 原文:[https://www . geesforgeks . org/big integer-pow-method-in-Java/](https://www.geeksforgeeks.org/biginteger-pow-method-in-java/)

**T1 大整数。幂(int index)**方法用于计算一个大整数，该大整数是作为指数传递的某个其他数字的幂，该指数的值等于(this) <sup>指数</sup>。此方法对调用此方法的当前 BigInteger 执行操作，并将指数作为参数传递。
**语法:**

```
public BigInteger pow(int exponent)
```

**参数:**这个方法接受一个参数**指数**，它是这个大整数应该被提升到的指数。
**返回:**
该方法返回一个等于(this) <sup>指数</sup>的大整数。
**异常:**
参数指数必须为正数(指数> = 0)，否则抛出**算术异常**。
**示例:**

```
Input: BigInteger1=321456, exponenet=5
Output: 3432477361331488865859403776
Explanation: BigInteger1.pow(exponent)=3432477361331488865859403776\. 
321456^5=3432477361331488865859403776

Input: BigInteger1=45321, exponenet=3
Output: 93089018611161
Explanation: BigInteger1.pow(exponent)=93089018611161\. 
321456^5=93089018611161

```

**下面的程序举例说明 BigInteger 类**
**的 pow()方法示例 1:**

```
// Java program to demonstrate 
// pow() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {

        // Creating BigInteger object
        BigInteger b1;

        b1 = new BigInteger("321456");
        int exponent = 5;

        // apply pow() method
        BigInteger result = b1.pow(exponent);

        // print result
        System.out.println("Result of pow operation between BigInteger " 
             + b1 + " and exponent " + exponent + " equal to " + result);
    }
}
```

**输出:**

> 大整数 321456 和等于 3432477361331488658594 的指数 5 之间的幂运算的结果 34324773613 3314 4886585 588594 588585 58885

例 2:

```
// Java program to demonstrate
// pow() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {

        // Creating BigInteger object
        BigInteger b1;

        b1 = new BigInteger("12346");
        int exponent = 6;

        // apply pow() method
        BigInteger result = b1.pow(exponent);

        // print result
        System.out.println("Result of pow operation between BigInteger "
             + b1 + " and exponent " + exponent + " equal to " + result);
    }
}
```

**输出:**

> BigInteger 41432345678 和等于 50586790764875298939353703126174303188973076418641741745274855 504 指数 6 之间幂运算的结果

**示例 3:**
当作为参数传递的指数小于零时显示异常的程序。

```
// Java program to demonstrate 
// pow() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {

        // Creating BigInteger object
        BigInteger b1;

        b1 = new BigInteger("76543");
        int exponent = -17;

        try {

        // apply pow() method
        BigInteger result = b1.pow(exponent);

        // print result
        System.out.println("Result of pow operation between " + b1
                           + " and " + exponent + " equal to " + result);
          } 
        catch (Exception e) { 
            System.out.println(e); 
        }

    }
}
```

**输出:**

> java.lang.ArithmeticException:负指数

**参考:**[https://docs . Oracle . com/en/Java/javae/12/docs/API/Java . base/Java/math/biginteger . html # pow(int)](https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigInteger.html#pow(int))