# Java 中的 BigInteger xor()方法

> 原文:[https://www . geesforgeks . org/big integer-xor-method-in-Java/](https://www.geeksforgeeks.org/biginteger-xor-method-in-java/)

**先决条件:** [大整数基础知识](https://www.geeksforgeeks.org/biginteger-class-in-java/)
**异或(大整数值)**方法返回两个大整数的按位异或。当且仅当当前 bigInteger 和传入参数 id 的 bigInteger 中恰好有一个为负时，此方法返回负 BigInteger。BigInteger 类的 xor()方法对作为参数传递的当前 BigInteger 和 BigInteger 应用按位异或运算。

**语法:**

```
public BigInteger xor(BigInteger val)
```

**参数:**该方法接受一个大整数类型的参数*值*，并引用要与该大整数异或的值。

**返回值:**该方法返回当前大整数与大整数*值*的按位异或。

**示例:**

```
Input: value1 = 2300 , value2 = 3400
Output: 1460
Explanation:
Binary of 2300 = 100011111100
Binary of 3400 = 110101001000
XOR of 100011111100 and 110101001000 = 10110110100
Decimal of 10110110100 = 1460.

Input: value1 = 54298 , value2 = 64257
Output: 12059

```

下面的程序说明了大整数类的异或()方法:

```
/*
*Program Demonstrate xor() method of BigInteger 
*/
import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Create 2 BigInteger objects
        BigInteger biginteger = new BigInteger("2300");
        BigInteger val = new BigInteger("3400");

        // Call xor() method to find this ^ val
        BigInteger biggerInteger = biginteger.xor(val);

        String result = "Result of XOR operation between " + biginteger + " and "
                        + val + " is " + biggerInteger;

        // Print result
        System.out.println(result);
    }
}
```

**参考:**[https://docs . Oracle . com/javae/7/docs/API/Java/math/big integer . html # xorg(Java . math . big integer)](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#xor(java.math.BigInteger))