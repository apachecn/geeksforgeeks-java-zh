# Java 中的 BigInteger shiftRight()方法

> 原文:[https://www . geesforgeks . org/big integer-shift right-method-in-Java/](https://www.geeksforgeeks.org/biginteger-shiftright-method-in-java/)

**先决条件:** [大整数基础知识](https://www.geeksforgeeks.org/biginteger-class-in-java/)

方法返回一个大整数，其值为(这个> > n)。移位距离 n 可以是负的，在这种情况下，该方法执行左移。shiftRight()方法将一个数字的二进制表示中的每个数字向右移动 n 次，并且移位方向上的最后一位被替换为 0。这个 shiftRight()方法计算楼层(这个/ 2^n).

**语法:**

```
public BigInteger shiftRight(*int n*)
```

**参数:**该方法取整数型的一个参数 *n* ，该参数指的是以比特为单位的移位距离。

**返回值:**该方法将位向右移位 n 次后返回大整数。

**异常:**如果移动距离是整数，该方法可能会抛出*算术异常*。最小值。

**例:**

```
Input: BigInteger = 2300, n = 3
Output: 287
Explanation:
Binary Representation of 2300 = 100011111100
Shift distance, n = 3\. 
After shifting 100011111100 right 3 times,
Binary Representation becomes 100011111
and Decimal equivalent of 100011111 is 287.

Input: BigInteger = 35000, n = 5
Output: 1093

```

下面的程序说明了 BigInteger 的 shiftRight(索引)方法:

```
// Program to demonstrate shiftRight()
// method of BigInteger 

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Create BigInteger object
        BigInteger biginteger = new BigInteger("2300");

        // Create a int i for Shift Distance
        int i = 3;

        // Call shiftRight() method on bigInteger at index i
        // store the return value as BigInteger
        BigInteger changedvalue = biginteger.shiftRight(i);

        String result = "After applying shiftRight by Shift Distance " + i + 
        " on " + biginteger + " New Value is " + changedvalue;

        // Print result
        System.out.println(result);
    }
}
```

**输出:**

```
After applying shiftRight by Shift Distance 3 on 2300 New Value is 287

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/biginteger . html # shift right(int)](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#shiftRight(int))