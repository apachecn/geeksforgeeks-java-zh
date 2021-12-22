# Java 中的 BigInteger 或()方法

> 原文:[https://www.geeksforgeeks.org/biginteger-or-method-in-java/](https://www.geeksforgeeks.org/biginteger-or-method-in-java/)

先决条件:[大整数基础知识](https://www.geeksforgeeks.org/biginteger-class-in-java/)

**Java . math . BigInteger . OR(BigInteger val)**方法用于对两个 BigInteger 执行按位或运算。一个 BigInteger 传入参数，另一个调用函数。如果函数使用的任一个大整数为负数，则此方法返回负数。BigInteger 的 OR()方法对作为参数传递的当前 bigInteger 和 bigInteger 应用按位“或”运算。

**语法:**

```
public BigInteger or(BigInteger val)
```

**参数:**该方法接受一个大整数类型的参数*值*，并引用该大整数的“或”值。

**返回值:**该方法返回当前大整数与大整数*值*的按位或。

**例:**

```
Input: value1 = 2300 , value2 = 3400
Output: 3580
Explanation:
Binary of 2300 = 100011111100
Binary of 3400 = 110101001000
OR of 100011111100 and 110101001000 = 110111111100
Decimal of 110111111100 = 3580.

Input: value1 = 54298 , value2 = 64257
Output: 65307

```

下面程序举例说明 BigInteger 类的 or()方法:

```
/*
*Program Demonstrate or() method of BigInteger 
*/
import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Creates 2 BigInteger objects
        BigInteger biginteger = new BigInteger("2300");
        BigInteger val = new BigInteger("3400");

        // Call or() method to find (biginteger | val)
        BigInteger biggerInteger = biginteger.or(val);

        String result = "Result of OR operation between " + biginteger + " and "
                        + val + " is " + biggerInteger;

        // Print result
        System.out.println(result);
    }
}
```

**输出:**

```
Result of OR operation between 2300 and 3400 is 3580

```

**参考:**[https://docs . Oracle . com/javae/7/docs/API/Java/math/big integer . html # or(Java . math . big integer)](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#or(java.math.BigInteger))