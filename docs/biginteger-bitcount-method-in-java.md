# Java 中的 BigInteger bitCount()方法

> 原文:[https://www . geesforgeks . org/big integer-bit count-method-in-Java/](https://www.geeksforgeeks.org/biginteger-bitcount-method-in-java/)

先决条件:[大整数基础知识](https://www.geeksforgeeks.org/biginteger-class-in-java/)
**方法返回这个大整数的二进制补码表示中与其符号位不同的位数。当在大整数上实现位向量样式集时，此方法很有用。
**语法:**** 

```
public int bitCount()
```

**参数:**该方法不取任何参数。
**返回值:**该方法用于返回这个大整数的二进制补码表示中与其符号位不同的位数。
**例:**

```
Input: value = 2300 
Output: 7
Explanation:
Binary signed 2's complement of 2300 = 0000100011111100
Singned bit is 0 because 2300 is positive
so no of 1 in 0000100011111100 is bitCount
So bitCount in 0000100011111100 = 7

Input: value = 5482549
Output: 11
```

下面的程序说明了 BigInteger 的 bitCount()方法。

## Java 语言(一种计算机语言，尤用于创建网站)

```
/*
*Program Demonstrate bitCount() method of BigInteger
*/
import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Creates  BigInteger objects
        BigInteger biginteger = new BigInteger("2300");

        // Calling bitCount() method on bigInteger
        int count = biginteger.bitCount();

        String result = "BitCount of  " + biginteger + " is " + count;

        // Print result
        System.out.println(result);
    }
}
```

**Output:** 

```
BitCount of  2300 is 7
```

**参考:**[https://docs . Oracle . com/javae/7/docs/API/Java/math/big integer . html # bit count()](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#bitCount())