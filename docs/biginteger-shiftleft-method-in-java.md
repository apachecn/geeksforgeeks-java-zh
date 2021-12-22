# Java 中的 BigInteger shiftLeft()方法

> 原文:[https://www . geesforgeks . org/big integer-shift left-method-in-Java/](https://www.geeksforgeeks.org/biginteger-shiftleft-method-in-java/)

**Java . math . BigInteger . shift left(int n)**方法返回一个 BigInteger，其值为(这个< < n)。移位距离 n 可以是负的，在这种情况下，该方法执行右移位。shiftLeft()方法将数字的二进制表示中的每个数字向左移动 n 次，并且移位方向上的最后一位被 0 替换。这个 ShiftLeft()方法计算*楼层(这个* 2^n)* 。

**语法:**

```
public BigInteger shiftLeft(int n)
```

**参数:**该方法取整数型的一个参数 *n* ，以位为单位，表示移位距离。

**返回值:**该方法将比特左移 n 次后返回大整数。

**异常:**如果移动距离为整数，该方法可能会抛出*算术异常*。最小值。

**例:**

```
Input: value = 2300, shift distance = 3
Output: 18400
Explanation:
Binary Representation of 2300 = 100011111100
shift distance = 3
after shifting 100011111100 left 3 times then
Binary Representation becomes 100011111100000
and Decimal equivalent of 100011111100000 is 18400.

Another way of expressing the same can be 2300*(2^3)=18400

Input: value = 35000, index = 5
Output: 1120000

```

下面的程序说明了 BigInteger 的 shiftLeft(索引)方法。

```
// Program to demonstrate shiftLeft() method of BigInteger 

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Creating BigInteger object
        BigInteger biginteger = new BigInteger("2300");

        // Creating a int i for Shift Distance
        int i = 3;

        // Call shiftLeft() method on bigInteger at index i
        // store the return value as BigInteger
        BigInteger changedvalue = biginteger.shiftLeft(i);

        String result = "After applying ShiftLeft by Shift Distance " + i
                        + " on " + biginteger + " New Value is " + changedvalue;

        // Printing result
        System.out.println(result);
    }
}
```

**输出:**

```
After applying ShiftLeft by Shift Distance 3 on 2300 New Value is 18400

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/biginteger . html # shift left(int)](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#shiftLeft(int))