# Java 中的 BigInteger testBit()方法

> 原文:[https://www . geesforgeks . org/big integer-testbit-method-in-Java/](https://www.geeksforgeeks.org/biginteger-testbit-method-in-java/)

**先决条件:** [【大整数基础知识】](https://www.geeksforgeeks.org/biginteger-class-in-java/)
**Java . math . big integer . testbit(*index*)**方法在且仅在设置了指定位的情况下返回 true。此方法计算*(此& (1 < < n))！= 0)* 。

**语法:**

```java
public boolean testBit(*int n*)
```

**参数:**该方法取整数型的一个参数 *n* ，指需要测试的位的索引。

**返回值:**当且仅当指定位被置位时，该方法返回真，否则返回假。

**异常:**当 n 为负时，该方法将抛出*算术异常*。
**例:**

```java
Input: BigInteger = 2300, n = 4
Output: true
Explanation:
Binary Representation of 2300 = 100011111100
bit at index 4 is 1 so set it means bit is set
so method will return true

Input: BigInteger = 5482549 , n = 1
Output: false

```

下面的程序说明了 BigInteger 的 testBit()方法。

```java
// Program to demonstrate the testBit()
// method of BigInteger

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {
        // Creating a BigInteger object
        BigInteger biginteger = new BigInteger("2300");

        // Creating an int i for index
        int i = 3;

        boolean flag = biginteger.testBit(i);

        String result = "The bit at index " + i + " of " + 
        biginteger + " is set = " + flag;

        // Displaying the result
        System.out.println(result);
    }
}
```

**Output:**

```java
The bit at index 3 of 2300 is set = true

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/biginteger . html # testBit(int)](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#testBit(int))