# Java 中的 BigInteger sqrt()方法

> 原文:[https://www . geesforgeks . org/big integer-sqrt-method-in-Java/](https://www.geeksforgeeks.org/biginteger-sqrt-method-in-java/)

**Java . math . BigInteger . byteevalueexact()**是在 Java SE 9 & JDK 9 中添加的内置函数**，该函数返回应用了 sqrt()方法的 BigInteger 的平方根的 big integer 值。它与 floor(sqrt(n))相同，其中 n 是一个数字。如果实平方根不能表示为整数值，则该平方根小于实平方根。**

**语法:**

```
public BigInteger sqrt()
```

**参数:**该方法不取任何参数。
**返回值:**方法返回这个大整数的整数平方根。
**异常:**如果 BigInteger 为负，则该方法将抛出 ArithmeticException。

**示例:**

```
Input: 234876543456
Output: 484640
Explanation: 122 is given as input which is the bigInteger.
The square root of 122 is 11.04536
whose BigInteger equivalent is 11 and using sqrt()
method of BigInteger class we can get
Square root of any BigInteger.

Input: 122
Output: 11
```

下面的程序说明了 BigInteger 类的 sqrt()方法:

**程序 1:** 展示应用 sqrt()方法得到 31739 的平方根。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Please run this program in JDK 9 or JDK 10
// Java program to demonstrate sqrt() method
import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Creating a BigInteger object
        BigInteger big, squareRoot;

        big = new BigInteger("31739");

        // calculate square root o bigInteger
        // using sqrt() method
        squareRoot = big.sqrt();

        // print result
        System.out.println("Square root value of BigInteger " + big
                           + " is " + squareRoot);
    }
}
```

**输出:**

```
Square root value of BigInteger 31739 is 178
```

**程序 2:** 显示 sqrt()方法抛出的异常。

## Java 语言(一种计算机语言，尤用于创建网站)

```
//Please run this program in JDK 9 or JDK 10
// Java program to demonstrate sqrt() method
//and exception thrown by it
import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Creating a BigInteger object
        BigInteger big,squareRoot=null;

        big = new BigInteger("-2345");

        //calculate square root o bigInteger
        //using sqrt() method
        try {
            squareRoot = big.sqrt();
        } catch (Exception e) {
            e.printStackTrace();
        }

        // print result
        System.out.println("Square root value of BigInteger " + big
                +" is "+squareRoot);
    }
}
```

**输出:**

```
java.lang.ArithmeticException: Negative BigInteger
    at java.base/java.math.BigInteger.sqrt(Unknown Source)
    at GFG.main(GFG.java:19)
Square root value of BigInteger -2345 is null
```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/math/biginteger . html # sqrt–](https://docs.oracle.com/javase/9/docs/api/java/math/BigInteger.html#sqrt--)