# Java 中的 BigInteger getLowestSetBit()方法

> 原文:[https://www . geesforgeks . org/big integer-getlowestsetbit-method-in-Java/](https://www.geeksforgeeks.org/biginteger-getlowestsetbit-method-in-java/)

**先决条件:** [大整数基础知识](https://www.geeksforgeeks.org/biginteger-class-in-java/)

**Java . math . BigInteger . getLowestSetBit()**方法返回这个 BigInteger 最右边(最低阶)集合位的索引。这意味着此方法返回最右边设置位右边的零位或未设置位的数量。如果 BigInteger 不包含设置位，那么这个方法将返回-1。该方法计算*(这个大整数==0？-1:log2(this big integer&-this big integer))*。

**语法:**

```
public int getLowestSetBit()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回这个大整数中最右边设置位的索引。

**例:**

```
Input: value = 2300 
Output: 2
Explanation:
Binary Representation of 2300 = 100011111100
The lowest set bit index is 2

Input: value = 35000 
Output: 3

```

下面程序举例说明了 getLowestSetBit()方法的 BigInteger:

```
// Program to illustrate the getLowestSetBit()
// method of BigInteger 

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Create BigInteger object
        BigInteger biginteger = new BigInteger("2300");

        // Call getLowestSetBit() method on bigInteger
        // Store the return value as Integer lowestsetbit
        int lowestSetbit = biginteger.getLowestSetBit();

        String lsb = "After applying getLowestSetBit on " + biginteger +
                       " we get index of lowest set bit = " + lowestSetbit;

        // Printing result
        System.out.println(lsb);
    }
}
```

**输出:**

```
After applying getLowestSetBit on 2300 we get index of lowest set bit = 2

```

**参考:**[https://docs . Oracle . com/javae/7/docs/API/Java/math/big integer . html # get test bit()](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#getLowestSetBit())