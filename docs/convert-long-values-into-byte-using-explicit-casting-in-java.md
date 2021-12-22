# 在 Java 中使用显式转换将长值转换为字节

> 原文:[https://www . geesforgeks . org/convert-long-values-in-byte-using-explicit-casting-in-Java/](https://www.geeksforgeeks.org/convert-long-values-into-byte-using-explicit-casting-in-java/)

在 Java 中，一个字节只能包含-128 到 127 之间的值，如果我们试图将一个长值转换为高于或低于该字节的限制，那么将会有精度损失。

**1。** **字节:**字节数据类型是一个 8 位有符号二进制补码整数。

**语法:**

```java
byte varName; // Default value 0

```

**值:**

```java
1 byte (8 bits) : 
-128 to 127

```

**2。long:** 长数据类型是 64 位二进制补码整数。

**语法:**

```java
long varName; // Default value 0

```

**值:**

```java
8 byte (64 bits):
-9223372036854775808 to 9223372036854775807

```

**例 1:** 在限值内

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Convert Long (under Byte limit)
// Values into Byte using explicit casting
import java.io.*;

class GFG {

    public static void main(String[] args)
    {
        long firstLong = 45;
        long secondLong = -90;

        // explicit type conversion from long to byte
        byte firstByte = (byte)firstLong;
        byte secondByte = (byte)secondLong;

        // printing typecasted value
        System.out.println(firstByte);
        System.out.println(secondByte);
    }
}
```

**Output**

```java
45
-90

```

**例 2:** 超出限制

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Convert Long (out of the
// limits of Byte) Values into Byte using 
// explicit casting

import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        long firstLong = 150;
        long secondLong = -130;

        // explicit type conversion from long to byte
        byte firstByte = (byte)firstLong;
        byte secondByte = (byte)secondLong;

        // printing typecasted value
        System.out.println(firstByte);
        System.out.println(secondByte);
    }
}
```

**Output**

```java
-106
126

```