# Java 中的 BigInteger toByteArray()方法

> 原文:[https://www . geesforgeks . org/big integer-tobytearray-method-in-Java/](https://www.geeksforgeeks.org/biginteger-tobytearray-method-in-java/)

**Java . math . BigInteger . toBytearray()**方法返回一个字节数组，其中包含这个 BigInteger 的二进制补码表示。字节数组的最高有效字节出现在第零个元素中。从这个方法返回的数组包含一个位，并包含表示这个大整数所需的最小字节数。符号位位置为**(ceil((this . bit length()+1)/8))**。

**语法:**

```java
public byte[] toByteArray()
```

**参数**:该方法不接受任何参数。

**返回值:**这个方法返回一个字节数组，包含这个大整数的二进制补码表示。

下面的程序说明了 BigInteger 类的 toByteArray()方法:

**例 1:**

```java
// Java program to demonstrate toByteArray() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {

        // Creating BigInteger object
        BigInteger bigInt = BigInteger.valueOf(10);

        // create a byte array
        byte b1[];
        b1 = bigInt.toByteArray();

        // print result
        System.out.print("ByteArray of BigInteger "
                         + bigInt + " is");

        for (int i = 0; i < b1.length; i++) {
            System.out.format(" "
                                  + "0x%02X",
                              b1[i]);
        }
    }
}
```

**输出:**

```java
ByteArray of BigInteger 10 is 0x0A

```

**例 2:**

```java
// Java program to demonstrate toByteArray() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {

        // create byte array
        byte b[] = { 0x1, 0x2, 0x1 };

        // Creating BigInteger object using byte Array
        BigInteger bigInt = new BigInteger(b);

        // apply toByteArray() on BigInteger
        byte b1[] = bigInt.toByteArray();

        // print result
        System.out.print("ByteArray of BigInteger "
                         + bigInt + " is");

        for (int i = 0; i < b1.length; i++) {
            System.out.format(" "
                                  + "0x%02X",
                              b1[i]);
        }
    }
}
```

**输出:**

```java
ByteArray of BigInteger 66049 is 0x01 0x02 0x01

```

**参考:**[https://docs . Oracle . com/javae/7/docs/API/Java/math/big integer . html # Toby array()](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#toByteArray())