# Java 中的 BigDecimal movePointLeft()方法

> 原文:[https://www . geesforgeks . org/big decimal-movepointleft-method-in-Java/](https://www.geeksforgeeks.org/bigdecimal-movepointleft-method-in-java/)

**先决条件:** [大十进制基础知识](https://www.geeksforgeeks.org/bigdecimal-class-java/)

**Java . math . BigDecimal . movepointleft(*int n*)**方法用于将当前 BigDecimal 的小数点向左移动 n 位。

*   如果 n 是非负数，则调用只是将 n 加到刻度上。
*   如果 n 为负，则调用相当于 movePointRight(-n)。

此方法返回的 BigDecimal 值有值(this × 10-n)和最大刻度(this.scale()+n，0)。

**语法:**

```
public BigDecimal movePointLeft(*int n*)
```

**参数:**该方法取整数型的一个参数 *n* ，指小数点需要左移的位数。

**返回值:**方法返回相同的 BigDecimal 值，小数点左移 n 位。

**异常:**如果刻度溢出，方法抛出*算法异常*。
**例:**

```
Input: value = 2300.9856, Leftshift = 3
Output: 2.3009856
Explanation:
while shifting the decimal point of 2300.9856 
by 3 places to the left, 2.3009856 is obtained
Alternate way: 2300.9856*10^(-3)=2.3009856

Input: value = 35001, Leftshift = 2
Output: 350.01

```

下面的程序说明了大十进制的 movePointLeft()方法:

```
// Program to demonstrate movePointLeft() method of BigDecimal 

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Create BigDecimal object
        BigDecimal bigdecimal = new BigDecimal("2300.9856");

        // Create a int i for decimal left move distance
        int i = 3;

        // Call movePointLeft() method on BigDecimal by shift i
        // Store the return value as BigDecimal
        BigDecimal changedvalue = bigdecimal.movePointLeft(i);

        String result = "After applying decimal move left by move Distance " 
        + i + " on " + bigdecimal + " New Value is " + changedvalue;

        // Print result
        System.out.println(result);
    }
}
```

**Output:**

```
After applying decimal move left by move Distance 3 on 2300.9856 New Value is 2.3009856

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/bigdecimal . html # movePointLeft(int)](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#movePointLeft(int))