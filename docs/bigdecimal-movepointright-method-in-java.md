# Java 中的 BigDecimal movePointRight()方法

> 原文:[https://www . geesforgeks . org/big decimal-movepointright-method-in-Java/](https://www.geeksforgeeks.org/bigdecimal-movepointright-method-in-java/)

**先决条件:** [大十进制基础知识](https://www.geeksforgeeks.org/bigdecimal-class-java/)

**Java . math . BigDecimal . movepointright(*int n*)**方法用于将当前 BigDecimal 的小数点向右移动 n 位。

*   If n is non-negative, the call simply subtracts n from the scale.
*   If n is negative, the call is equivalent to movePointLeft(-n).

此方法返回的 BigDecimal 具有值(this × 10n)和最大刻度(this.scale()-n，0)。

**语法:**

```java
public BigDecimal movePointRight(*int n*)
```

**参数:**该方法取整数型的一个参数 *n* ，指小数点需要向右移动的位数。

**返回值:**该方法返回相同的 BigDecimal 值，小数点向右移动 n 位。

**异常:**如果刻度溢出，方法抛出*算法异常*。

**例:**

```java
Input: value = 2300.9856, rightshift = 3
Output: 2300985.6
Explanation:
After shifting the decimal point of 2300.9856 by 3 places to right,
2300985.6 is obtained.
Alternate way: 2300.9856*10^(3)=2300985.6

Input: value = 35001, rightshift = 2
Output: 3500100

```

下面的程序说明了大十进制的 movePointRight()方法:

```java
// Program to demonstrate movePointRight() method of BigDecimal 

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {
        // Create BigDecimal object
        BigDecimal bigdecimal = new BigDecimal("2300.9856");

        // Create a int i for decimal right move distance
        int i = 3;

        // Call movePointRight() method on BigDecimal by shift i
        BigDecimal changedvalue = bigdecimal.movePointRight(i);

        String result = "After applying decimal move right
        by move Distance " + i + " on " + bigdecimal + 
        " New Value is " + changedvalue;

        // Print result
        System.out.println(result);
    }
}
```

**输出:**

```java
After applying decimal move right by move Distance 3 on 2300.9856 New Value is 2300985.6

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/bigdecimal . html # movePointRight(int)](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#movePointRight(int))