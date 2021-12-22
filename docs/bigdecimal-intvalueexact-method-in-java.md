# Java 中的 BigDecimal intvalueExact()方法

> 原文:[https://www . geesforgeks . org/big decimal-int value exact-method-in-Java/](https://www.geeksforgeeks.org/bigdecimal-intvalueexact-method-in-java/)

**Java . math . BigDecimal . int value exact()**是一个内置函数，它将*这个* BigDecimal 转换为一个整数值，并检查丢失的信息。如果此 BigDecimal 有任何小数部分，或者转换结果太大而无法表示为整数值，此函数将引发算术异常。

**语法:**

```java
public int intValueExact()
```

**参数:**此功能不接受参数。

**返回值:**该函数返回*这个*大十进制的整数值。

**异常:**如果这个 BigDecimal 中有一个非零小数部分或者它的值太大而不能表示为整数，那么函数会抛出*算术异常*。

**示例:**

```java
Input : "19878124"
Output : 19878124

Input : "721111"
Output : 721111

```

下面的程序说明了 Java . math . bigdecimal . intvalueexact()方法的使用:
**程序 1:**

```java
// Java program to illustrate
// intValueExact() method
import java.math.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        // Creating 2 BigDecimal Objects
        BigDecimal b1, b2;
        // Assigning values to b1, b2
        b1 = new BigDecimal("19878124");
        b2 = new BigDecimal("721111");
        // Displaying their respective Integer Values
        System.out.println("Exact Integer Value of " +
        b1 + " is " + b1.intValueExact());
        System.out.println("Exact Integer Value of " +
        b2 + " is " + b2.intValueExact());
    }
}
```

**Output:**

```java
Exact Integer Value of 19878124 is 19878124
Exact Integer Value of 721111 is 721111

```

**注意:**与 intValue()函数不同，该函数丢弃了*的任何小数部分* BigDecimal，当转换结果太大而无法表示为整数值时，只返回低阶 32 位，在这种情况下，该函数抛出*算术异常*。

**程序 2:** 该程序将说明该函数何时抛出异常。

```java
// Java program to illustrate
// Arithmetic Exception occurrence
// in intValueExact() method
import java.math.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        // Creating 2 BigDecimal Objects
        BigDecimal b1, b2;

        // Assigning values to b1, b2
        b1 = new BigDecimal("3232435121868179");
        b2 = new BigDecimal("84561789104423214");

        // Displaying their respective Integer Values
        // using intValue()
        System.out.println("Output by intValue() Function");
        System.out.println("The Integer Value of " + 
        b1 + " is " + b1.intValue());
        System.out.println("The Integer Value of " + 
        b2 + " is " + b2.intValue());

        // Exception handling
        System.out.println("\nOutput by intValueExact() Function");
        try {
            System.out.println("Exact Integer Value of " + 
            b1 + " is " + b1.intValueExact());
            System.out.println("Exact Integer Value of " + 
            b2 + " is " + b2.intValueExact());
        }
        catch (ArithmeticException e) {
            System.out.println("Arithmetic Exception caught");
        }
    }
}
```

**Output:**

```java
Output by intValue() Function
The Integer Value of 3232435121868179 is -214774381
The Integer Value of 84561789104423214 is -920387282

Output by intValueExact() Function
Arithmetic Exception caught

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/bigdecimal . html # intValueExact()](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#intValueExact())