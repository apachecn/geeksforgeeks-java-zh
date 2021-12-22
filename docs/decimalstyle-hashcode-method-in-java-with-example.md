# Java 中的十进制样式 hashCode()方法，示例

> 原文:[https://www . geesforgeks . org/decimal style-hashcode-method-in-Java-with-example/](https://www.geeksforgeeks.org/decimalstyle-hashcode-method-in-java-with-example/)

java 中**Java . time . format . DecimalStyle 类**的 **hashCode()** 方法用来获取这个 decimal style 的 hashCode 值。这个方法返回一个代表 hashCode 值的整数。

**语法:**

```java
public int hashCode()

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回一个**整数值**，这是这个十进制样式的哈希值。

**异常:**这个方法不抛出任何异常。

**程序:**

```java
// Java program to demonstrate
// the above method

import java.time.format.*;
import java.util.*;

public class DecimalStyleDemo {
    public static void main(String[] args)
    {

        DecimalStyle ds1
            = DecimalStyle.STANDARD;

        DecimalStyle ds2
            = DecimalStyle.of(new Locale("JAPANESE"));

        System.out.println("HashCode value of DS 1: "
                           + ds1.hashCode());

        System.out.println("HashCode value of DS 2: "
                           + ds2.hashCode());
    }
}
```

**输出:**

```java
HashCode value of DS 1: 182
HashCode value of DS 2: 182

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/format/decimal style . html # hashCode()](https://docs.oracle.com/javase/10/docs/api/java/time/format/DecimalStyle.html#hashCode())