# Java 中 BigDecimal hashCode()方法

> 原文:[https://www . geesforgeks . org/big decimal-hashcode-method-in-Java/](https://www.geeksforgeeks.org/bigdecimal-hashcode-method-in-java/)

**Java . math . big decimal . hashcode()**返回这个 BigDecimal 的哈希代码*。对于两个值相等但比例不同的 BigDecimal 对象(如 4743.0 和 4743.00)，hashcode 通常不会相同。*

**语法:**

```
public int hashCode()
```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回一个整数值，该整数值等于大十进制对象的哈希值。

**示例:**

```
Input : BigDecimal = 67891    
Output : Hashcode : 2104621

Input : BigDecimal = 67891.000
Output : Hashcode : 2104621003

```

下面的程序说明了 BigDecimal 类的 hashCode()函数:
**程序 1:**

```
// Java program to demonstrate hashCode() method
import java.io.*;
import java.math.*;

public class GFG {

    public static void main(String[] args)
    {
        // Creating a BigDecimal object
        BigDecimal b;

        // Assigning value
        b = new BigDecimal(4743);
        System.out.print("HashCode for " + b + " is ");
        System.out.println(b.hashCode());
    }
}
```

**Output:**

```
HashCode for 4743 is 147033

```

**程序 2:** 该程序将说明两个不同的大小数的 hashcode 值相等但比例不同会有所不同。

```
// Java program to demonstrate hashCode() method
import java.io.*;
import java.math.*;

public class GFG {

    public static void main(String[] args)
    {
        // Creating 2 BigDecimal objects
        BigDecimal b1, b2;

        // Assigning values
        b1 = new BigDecimal("4743");
        b2 = new BigDecimal("4743.000");

        int i1, i2;

        i1 = b1.hashCode();
        i2 = b2.hashCode();

        if (i1 == i2) {
            System.out.println("HashCodes of " + 
            b1 + " and " + b2 + " are equal.");
            System.out.println("Both their HashCodes are " +
            i1 + ".");
        }
        else {
            System.out.println("HashCodes of " + b1 + " and " 
            + b2 + " are not equal.");
            System.out.println("HashCodes of " + b1 + " is " 
            + i1 + " and " + b2 + " is " + i2 + ".");
        }
    }
}
```

**Output:**

```
HashCodes of 4743 and 4743.000 are not equal.
HashCodes of 4743 is 147033 and 4743.000 is 147033003.

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/bigdecimal . html # hashCode()](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#hashCode())