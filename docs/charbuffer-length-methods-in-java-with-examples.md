# Java 中的 CharBuffer length()方法，示例

> 原文:[https://www . geesforgeks . org/char buffer-length-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/charbuffer-length-methods-in-java-with-examples/)

**java.nio.CharBuffer 类**的 **length()** 方法用来返回这个字符缓冲区的长度。当视为字符序列时，字符缓冲区的长度只是位置(包括)和限制(不包括)之间的字符数；也就是说，它相当于剩余()。

**语法:**

```java
public final int length()
```

**返回值:**这个方法返回这个字符缓冲区的长度。

下面是说明 length()方法的示例:

**示例 1:**

```java
// Java program to demonstrate
// length() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declare and initialize the char array
        char[] cb = { 'a', 'b', 'c' };

        // wrap the char array into CharBuffer
        // using wrap() method
        CharBuffer charBuffer = CharBuffer.wrap(cb);

        // Get the length of the charBuffer
        // using length() method
        int length = charBuffer.length();

        // print the byte buffer
        System.out.println("CharBuffer is : "
                           + Arrays.toString(
                                 charBuffer.array())
                           + "\nLength: "
                           + length);
    }
}
```

**输出:**

```java
CharBuffer is : [a, b, c]
Length: 3

```

**示例 2:**

```java
// Java program to demonstrate
// length() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // defining and allocating CharBuffer
        // using allocate() method
        CharBuffer charBuffer
            = CharBuffer.allocate(4);

        // append char value in charBuffer
        // using append() method
        charBuffer.append('a');
        charBuffer.append('b');

        // print the char buffer
        System.out.println("CharBuffer  before append : "
                           + Arrays.toString(
                                 charBuffer.array())
                           + "\nLength: "
                           + charBuffer.length());

        // append char value in charBuffer
        // using append() method
        charBuffer.append('c');

        // print the char buffer
        System.out.println("\nCharBuffer after append : "
                           + Arrays.toString(
                                 charBuffer.array())
                           + "\nLength: "
                           + charBuffer.length());
    }
}
```

**输出:**

```java
CharBuffer  before append : [a, b,,  ]
Length: 2

CharBuffer after append : [a, b, c,  ]
Length: 1

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/charbuffer . html # length–](https://docs.oracle.com/javase/9/docs/api/java/nio/CharBuffer.html#length--)