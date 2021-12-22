# Charset 是 Java 中的注册()方法，带有示例

> 原文:[https://www . geesforgeks . org/charset-is registered-method-in-Java-with-examples/](https://www.geeksforgeeks.org/charset-isregistered-method-in-java-with-examples/)

**isRegistered()** 方法是 **java.nio.charset** 的内置方法，用于检查给定的字符集是否在 [IANA 字符集注册表](http://www.iana.org/assignments/character-sets/character-sets.xhtml)下注册。

**语法** :

```java
public final boolean isRegistered()
```

**参数**:该功能不接受任何参数。

**返回值**:该函数返回一个布尔值。如果已注册，则返回 true，否则返回 false。

下面是上述功能的实现:

**程序 1:**

```java
// Java program to demonstrate
// the above function

import java.nio.charset.Charset;
import java.util.Iterator;
import java.util.Map;

public class GFG {

    public static void main(String[] args)
    {

        // Generate the Charset
        Charset first
            = Charset.forName("ISO-2022-CN");

        // Check if this Charset is registered
        System.out.println(first.isRegistered());
    }
}
```

**输出:**

```java
true

```

**程序二:**

```java
// Java program to demonstrate
// the above function

import java.nio.charset.Charset;
import java.util.Iterator;
import java.util.Map;

public class GFG {

    public static void main(String[] args)
    {

        // Generate the Charset
        Charset second
            = Charset.forName("x-windows-949");

        // Check if this Charset is registered
        System.out.println(second.isRegistered());
    }
}
```

**输出:**

```java
false

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/charset/charset . html # isRegistered–](https://docs.oracle.com/javase/9/docs/api/java/nio/charset/Charset.html#isRegistered--)