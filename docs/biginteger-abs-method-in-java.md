# Java 中的 BigInteger abs()方法

> 原文:[https://www . geesforgeks . org/big integer-ABS-method-in-Java/](https://www.geeksforgeeks.org/biginteger-abs-method-in-java/)

**先决条件:** [大整数基础知识](https://www.geeksforgeeks.org/biginteger-class-in-java/)

**Java . math . BigInteger . ABS()**方法返回 BigInteger 的绝对值。通过使用这种方法，人们可以找到以大整数形式存储的任何大数据量的绝对值。

**语法:**

```java
public BigInteger abs()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个大整数的绝对值。

**例:**

```java
Input: -2300 
Output: 2300
Explanation:
Applying mathematical abs() operation on 
-2300, positive 2300 is obtained i.e |-2300| = 2300\. 

Input: -5482549 
Output: 5482549

```

下面的程序说明了大整数的 abs()方法:

```java
// Below program illustrates the abs() method
// of BigInteger 

import java.math.*;

public class GFG {

public static void main(String[] args) {

        // Create BigInteger object
        BigInteger biginteger=new BigInteger("-2300");

        // abs() method on bigInteger to find the absolute value
        // of a BigInteger
        BigInteger absolutevalue= biginteger.abs();

        // Define result
        String result ="BigInteger "+biginteger+
            " and Absolute value is "+absolutevalue;
        // Print result 
        System.out.println(result);

    }
}
```

**输出:**

```java
BigInteger -2300 and Absolute value is 2300

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/biginteger . html # ABS()](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#abs())