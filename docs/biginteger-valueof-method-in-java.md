# Java 中的 BigInteger valueOf()方法

> 原文:[https://www . geesforgeks . org/big integer-value of-method-in-Java/](https://www.geeksforgeeks.org/biginteger-valueof-method-in-java/)

**Java . math . BigInteger . value of(长值)**方法返回一个 BigInteger，其值等于作为参数传递的 long 的值。这个方法是静态方法，所以不需要创建 BigInteger 类的对象来使用这个方法，我们可以通过 BigInteger.valueOf(长值)代码来调用这个函数。

**语法:**

```java
public static BigInteger valueOf(long val)
```

**参数:**该方法接受单个参数**值**，即要创建的大整数的值。

**返回值:**该方法返回**大整数**，其值等于作为参数传递的长值。

下面的程序说明了大整数类的 valueOf(长值)方法:

**示例 1:** 在不创建大整数对象的情况下应用()的值。

```java
// Java program to demonstrate valueOf() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {

        // Creating 2 BigInteger objects
        BigInteger b1, b2;

        // apply valueOf()
        b1 = BigInteger.valueOf(456782765);
        b2 = BigInteger.valueOf(12345543);

        // print result
        System.out.println("Value of BigInteger b1: " + b1);
        System.out.println("Value of BigInteger b2: " + b2);
    }
}
```

**输出:**

```java
Value of BigInteger b1: 456782765
Value of BigInteger b2: 12345543

```

**示例 2:** 通过创建大整数对象来应用()的值。

```java
// Java program to demonstrate valueOf() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {

        // Creating BigInteger objects
        BigInteger b1, b2, b3;

        // create bigInteger with some value
        b1 = new BigInteger("532721");

        // apply valueOf()
        b2 = b1.valueOf(234567898);
        b3 = b2.valueOf(98765432);

        // print result
        System.out.println("Value of BigInteger 1: " + b2);
        System.out.println("Value of BigInteger 2: " + b3);
    }
}
```

**输出:**

```java
Value of BigInteger 1: 234567898
Value of BigInteger 2: 98765432

```

**参考:**[https://docs . Oracle . com/javae/7/docs/API/Java/math/big integer . html # value of(long)](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#valueOf(long))