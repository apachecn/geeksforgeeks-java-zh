# Java 中的 Character.reverseBytes()，示例

> 原文:[https://www . geeksforgeeks . org/character-reverse bytes-in-Java-with-examples/](https://www.geeksforgeeks.org/character-reversebytes-in-java-with-examples/)

**java . lang . character . reverse bytes()**是 Java 中的一个内置方法，它返回通过反转指定字符值中字节的顺序而获得的值。

**语法:**

```java
public static char reverseBytes(char ch)

```

**参数:**函数接受一个强制参数 *ch* ，表示字节顺序颠倒的字符。

**返回:**该方法返回通过反转(或等效地，交换)指定字符值中的字节而获得的值。

下面的程序说明了 Java . lang . character . reverse bytes()函数:
**程序 1:**

```java
// Java program to demonstrate the
// Character.reverseBytes() when a

import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {

        // char whose byte order is to be reversed
        char c1 = '\u4d00';
        char c2 = Character.reverseBytes(c1);

        // prints the reversed bytes
        System.out.println("Reversing bytes on " + c1 + " gives " + c2);
    }
}
```

**Output:**

```java
Reversing bytes on ? gives M

```

**程序 2:**

```java
// Java program to demonstrate the
// Character.reverseBytes() when a
// number is passed

import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {

        // char whose byte order is to be reversed
        char c1 = '9';
        char c2 = Character.reverseBytes(c1);

        // prints the reversed bytes
        System.out.println("Reversing bytes on " + c1 + " gives " + c2);

        c1 = '7';
        c2 = Character.reverseBytes(c1);

        // prints the reversed bytes
        System.out.println("Reversing bytes on " + c1 + " gives " + c2);
    }
}
```

**Output:**

```java
Reversing bytes on 9 gives ?
Reversing bytes on 7 gives ?

```