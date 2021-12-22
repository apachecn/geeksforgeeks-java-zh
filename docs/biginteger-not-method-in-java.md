# Java 中的 BigInteger not()方法

> 原文:[https://www . geesforgeks . org/big integer-not-in-method-Java/](https://www.geeksforgeeks.org/biginteger-not-method-in-java/)

**Java . math . BigInteger . NOT()**方法用于查找 BigInteger 的按位非。当且仅当此 BigInteger 为非负值时，此方法返回负值。方法对当前的大整数应用按位非运算。

**语法:**

```java
public BigInteger not()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回与其一起使用的大整数的按位非值。

**例:**

```java
Input: value = 2300
Output: -2301
Explanation:
Binary of 2300 = 100011111100
NOT of 100011111100 in signed 2's complement is 1111011100000011
Decimal value = -2301.

Input: value = 567689 
Output: -567690

```

下面程序举例说明 BigInteger()的 not()方法:

```java
/*
*Program Demonstrate not() method of BigInteger 
*/
import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Creates  BigInteger object
        BigInteger biginteger = new BigInteger("2300");

        // Call not() method to find ~this
        BigInteger finalvalue = biginteger.not();
        String result = "Result of NOT operation on " + 
        biginteger + " is " + finalvalue;

        // Print result
        System.out.println(result);
    }
}
```

**输出:**

```java
Result of NOT operation on 2300 is -2301

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/big integer . html #和(java.math.BigInteger)](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#and(java.math.BigInteger))