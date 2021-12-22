# Java 中的 CharArrayReader read()方法，示例

> 原文:[https://www . geeksforgeeks . org/chararrayreader-read-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chararrayreader-read-method-in-java-with-examples/)

Java 中 **[CharArrayReader](https://www.geeksforgeeks.org/java-io-chararrayreader-class-java/)** 类的 **read()** 方法用于从流中读取单个字符。这个方法阻塞流直到:

*   It takes some input from the stream.
*   Some IOException occurred.
*   It has reached the end of the stream when reading.

此方法被声明为抽象方法。这意味着如果需要在读取字符时改变操作，CharArrayReader 抽象类的子类应该覆盖这个方法。

**语法:**

```java
public abstract int read()
```

**参数:**该方法不接受任何参数

**返回值:**该方法返回一个**整数值**，它是从流中读取的整数值。范围可以从 0 到 65535。否则，如果未读取任何字符，则返回-1。

**异常:**如果输入输出时出现错误，该方法抛出**异常**。

下面的方法说明了 read()方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// CharArrayReader read() method

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            char[] str = { 'G', 'e', 'e', 'k', 's',
                           'F', 'o', 'r',
                           'G', 'e', 'e', 'k', 's' };

            // Create a CharArrayReader instance
            CharArrayReader reader
                = new CharArrayReader(str);

            // Get the character
            // to be read from the stream
            int ch;

            // Read the first 5 characters
            // to this reader using read() method
            // This will put the str in the stream
            // till it is read by the reader
            for (int i = 0; i < 5; i++) {
                ch = reader.read();
                System.out.println("\nInteger value "
                                   + "of character read: "
                                   + ch);
                System.out.println("Actual "
                                   + "character read: "
                                   + (char)ch);
            }

            reader.close();
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
Integer value of character read: 71
Actual character read: G

Integer value of character read: 101
Actual character read: e

Integer value of character read: 101
Actual character read: e

Integer value of character read: 107
Actual character read: k

Integer value of character read: 115
Actual character read: s

```

**程序二:**

```java
// Java program to demonstrate
// CharArrayReader read() method

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        try {
            char[] str = { 'G', 'e', 'e', 'k', 's',
                           'F', 'o', 'r',
                           'G', 'e', 'e', 'k', 's' };

            // Create a CharArrayReader instance
            CharArrayReader reader
                = new CharArrayReader(str);

            // Get the character
            // to be read from the stream
            int ch;

            // Read the first character
            // to this reader using read() method
            // This will put the str in the stream
            // till it is read by the reader
            ch = reader.read();
            System.out.println("\nInteger value "
                               + "of character read: "
                               + ch);
            System.out.println("Actual "
                               + "character read: "
                               + (char)ch);

            reader.close();
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
Integer value of character read: 71
Actual character read: G

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/io/chararrayreader . html # read–](https://docs.oracle.com/javase/9/docs/api/java/io/CharArrayReader.html#read--)