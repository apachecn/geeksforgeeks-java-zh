# Java 中的 BigInteger andNot()方法

> 原文:[https://www . geesforgeks . org/big integer-and not-method-in-Java/](https://www.geeksforgeeks.org/biginteger-andnot-method-in-java/)

**Java . math . BigInteger . and not(BigInteger val)**方法返回一个 BigInteger，其值为(this&~ val)*this*为当前使用该函数的 big integer， *val* 为作为参数传递给该函数的 big integer。此方法等效于和(val.not())，为掩蔽操作提供了便利。当且仅当 BigInteger 为负且 val 为正时，此方法返回负的 big integer。andNOT()方法对作为参数传递的 bigInteger 的当前 bigInteger 和 NOT 值应用按位“与”运算。

**语法:**

```java
public BigInteger andNot(BigInteger val)
```

**参数:**该方法接受一个参数*值*大整数类型，是指需要用当前大整数进行补和的值。

**返回值:**该方法用于返回(此&~ val)*此*为当前使用该函数的大整数， *val* 为作为参数传递给该函数的大整数。

**例:**

```java
Input: value1 = 2300, value2 = 3400
Output: 180
Explanation:
Binary of 2300 = 100011111100
Not of 3400 in binary signed 2's complement is 1111001010110111
AND of 100011111100 and 1111001010110111= 10110100
Decimal of 10110100 = 180.

Input: value1 = 432045, value2 = 321076
Output: 135561

```

下面的程序说明了 BigInteger 的 andNot()方法。

```java
/*
*Program Demonstrate notNot() method of BigInteger 
*/
import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Create 2 BigInteger objects
        BigInteger biginteger = new BigInteger("2300");
        BigInteger val = new BigInteger("3400");

        // Call andNot() method to find this & ~val
        BigInteger finalvalue = biginteger.andNot(val);
        String result = "Result of andNot operation between " + 
        biginteger + " and "+ val + " is " + finalvalue;

        // Print the result
        System.out.println(result);
    }
}
```

**输出:**

```java
Result of andNot operation between 2300 and 3400 is 180

```

**参考:**[https://docs . Oracle . com/javae/7/docs/API/Java/math/big integer . html # and not(Java . math . big integer)](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#andNot(java.math.BigInteger))