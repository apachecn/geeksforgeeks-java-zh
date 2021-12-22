# Java 中的 BigInteger intValue()方法

> 原文:[https://www . geesforgeks . org/big integer-int value-method-in-Java/](https://www.geeksforgeeks.org/biginteger-intvalue-method-in-java/)

**Java . math . BigInteger . IntValue()**将这个 BigInteger 转换成一个整数值。如果这个函数返回的值太大，无法放入整数值，那么它将只返回低阶的 32 位。此外，这种转换可能会丢失关于 BigInteger 值的整体大小的信息。这个方法也可以返回符号相反的结果。

**语法:**

```java
public int intValue()
```

**返回:**该方法返回一个表示该大整数整数值的整数值。

**示例:**

```java
Input: BigInteger1=32145
Output: 32145
Explanation: BigInteger1.intValue()=32145.

Input: BigInteger1=4326516236135
Output: 1484169063
Explanation: BigInteger1.intValue()=1484169063\. This BigInteger is too big for 
intValue so it is returning lower 32 bit.

```

**示例 1:下面的程序说明了 BigInteger 类**的 intValue()方法

```java
// Java program to demonstrate 
// intValue() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {

        // Creating 2 BigInteger objects
        BigInteger b1, b2;

        b1 = new BigInteger("32145");
        b2 = new BigInteger("7613721");

        // apply intValue() method
        int intValueOfb1 = b1.intValue();
        int intValueOfb2 = b2.intValue();

        // print intValue
        System.out.println("intValue of "
                           + b1 + " : " + intValueOfb1);
        System.out.println("intValue of "
                           + b2 + " : " + intValueOfb2);
    }
}
```

**Output:**

```java
intValue of 32145 : 32145
intValue of 7613721 : 7613721

```

**例 2:当返回的整数对于 int 值来说太大时。**

```java
// Java program to demonstrate 
// intValue() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {

        // Creating 2 BigInteger objects
        BigInteger b1, b2;

        b1 = new BigInteger("4326516236135");
        b2 = new BigInteger("251362466336");

        // apply intValue() method
        int intValueOfb1 = b1.intValue();
        int intValueOfb2 = b2.intValue();

        // print intValue
        System.out.println("intValue of "
                           + b1 + " : " + intValueOfb1);
        System.out.println("intValue of "
                           + b2 + " : " + intValueOfb2);
    }
}
```

**Output:**

```java
intValue of 4326516236135 : 1484169063
intValue of 251362466336 : -2040604128

```

**参考:**
[大整数完整性()文件](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#intValue())