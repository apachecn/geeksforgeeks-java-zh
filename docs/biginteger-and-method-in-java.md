# Java 中的 BigInteger 和()方法

> 原文:[https://www . geesforgeks . org/big integer-and-method-in-Java/](https://www.geeksforgeeks.org/biginteger-and-method-in-java/)

**Java . math . BigInteger . AND(BigInteger val)**方法返回一个 BigInteger，其值是两个 BigInteger 的按位“与”。如果两个大整数都是负数，则此方法返回负数。and()方法对作为参数传递的当前大整数和大整数应用按位“与”运算。
**语法:**

```java
public BigInteger and(BigInteger val)
```

**参数:**该方法接受一个大整数类型的参数*值*，并引用要与当前大整数“与”的值。
**返回值:**该方法返回两个大整数的按位“与”的值。
**示例:**

```java
Input: value1 = 2300, value2 = 3400
Output: 2120
Explanation:
Binary of 2300 = 100011111100
Binary of 3400 = 110101001000
AND of 100011111100 and 110101001000 = 100001001000
Decimal of 100001001000 = 2120.

Input: value1 = 432045, value2 = 321076
Output: 296484
```

下面的程序用来说明 BigInteger 的 and()方法。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
/*
*Program Demonstrate and() method of BigInteger
*/
import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Creates 2 BigInteger objects
        BigInteger biginteger = new BigInteger("2300");
        BigInteger val = new BigInteger("3400");

        // Call and() method to find this & val
        BigInteger biggerInteger = biginteger.and(val);

        String result = "Result of AND operation between " + biginteger + " and "
                        + val + " is " + biggerInteger;

        // Print the result
        System.out.println(result);
    }
}
```

**Output:** 

```java
Result of AND operation between 2300 and 3400 is 2120
```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/big integer . html #和(java.math.BigInteger)](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#and(java.math.BigInteger))