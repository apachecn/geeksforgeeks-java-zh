# Java 中的 BigInteger 求反()方法

> 原文:[https://www . geesforgeks . org/big integer-否定方法 in-java/](https://www.geeksforgeeks.org/biginteger-negate-method-in-java/)

先决条件:[大整数基础知识](https://www.geeksforgeeks.org/biginteger-class-in-java/)
**方法返回一个值为(- this)的大整数。方法将改变 BigInteger 的信号位。**

**语法:**

```
public BigInteger negate()
```

**参数:**该方法不接受任何参数。

**返回值:**方法返回(- this)的运算。

**示例:**

```
Input: value = 2300
Output: -2300
Explanation:
Binary signed 2's complement of 2300 = 0000100011111100
Singed bit are 0000
change sing bit to 1111
so negate of 0000100011111100 in signed 2's complement is 1111011100000100
Decimal value = -2300.

Input: value = 567689 
Output: -567689 

```

下面的程序说明了 BigInteger 的否定()方法。

```
/*
*Program Demonstrate negate() method of BigInteger 
*/
import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Create  BigInteger object
        BigInteger biginteger = new BigInteger("2300");

        // Call negate() method to find -this
        BigInteger finalvalue = biginteger.negate();
        String result = "Result of negate operation on " + 
        biginteger + " is " + finalvalue;

        // Prints result
        System.out.println(result);
    }
}
```

**Output:**

```
Result of negate operation on 2300 is -2300

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/biginteger . html # negative()](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#negate())