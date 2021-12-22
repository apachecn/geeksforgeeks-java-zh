# Java 中的 BigDecimal longValueExact()方法

> 原文:[https://www . geesforgeks . org/big decimal-longvalueexact-method-in-Java/](https://www.geeksforgeeks.org/bigdecimal-longvalueexact-method-in-java/)

**Java . math . BigDecimal . longvalueexact()**是一个内置函数，它将*这个* BigDecimal 转换为一个长值，并检查丢失的信息。如果*这个*大十进制有任何小数部分，或者如果转换的结果太大而不能表示为长值，这个函数抛出算术异常。

**语法:**

```
public long longValueExact()
```

**参数:**此功能不接受任何参数。

**返回值:**该函数返回*这个*大十进制的长值。

**异常:**如果*这个* BigDecimal 中有非零小数部分或者其值太大无法表示为长，则函数抛出*算术异常*。

**示例:**

```
Input : "1987812456121"
Output : 1987812456121

Input : "721111"
Output : 721111

```

下面的程序说明了 Java . math . bigdecimal . longvalueexact()方法的使用:
**程序 1:**

```
// Java program to illustrate
// longValueExact() method
import java.math.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        // Creating 2 BigDecimal Objects
        BigDecimal b1, b2;

        // Assigning values to b1, b2
        b1 = new BigDecimal("267694723232");
        b2 = new BigDecimal("721111845617");

        // Displaying their respective Long Values
        System.out.println("Exact Long Value of " + 
        b1 + " is " + b1.longValueExact());
        System.out.println("Exact Long Value of " + 
        b2 + " is " + b2.longValueExact());
    }
}
```

**Output:**

```
Exact Long Value of 267694723232 is 267694723232
Exact Long Value of 721111845617 is 721111845617

```

**注意:**与 longValue()函数不同，long value()函数丢弃了*的任何小数部分，当转换结果太大而无法表示为长值时，该函数仅返回低阶 64 位，在这种情况下，该函数抛出*算术异常*。*

**程序 2:**

```
// Java program to illustrate
// Arithmetic Exception occurrence
// in longValueExact() method
import java.math.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        // Creating 2 BigDecimal Objects
        BigDecimal b1, b2;
        // Assigning values to b1, b2
        b1 = new BigDecimal("267694723232435121868");
        b2 = new BigDecimal("72111184561789104423");
        // Displaying their respective Long Values
        // using longValue()
        System.out.println("Output by longValue() Function");
        System.out.println("The Long Value of " + b1 + " is " + b1.longValue());
        System.out.println("The Long Value of " + b2 + " is " + b2.longValue());
        // Exception handling
        System.out.println("\nOutput by longValueExact() Function");
        try {
            System.out.println("Exact Long Value of " + 
            b1 + " is " + b1.longValueExact());
            System.out.println("Exact Long Value of " + 
            b2 + " is " + b2.longValueExact());
        }
        catch (ArithmeticException e) {
            System.out.println("Arithmetic Exception caught");
        }
    }
}
```

**Output:**

```
Output by longValue() Function
The Long Value of 267694723232435121868 is -9006437873208152372
The Long Value of 72111184561789104423 is -1675791733049102041

Output by longValueExact() Function
Arithmetic Exception caught

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/bigdecimal . html # longValueExact()](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#longValueExact())