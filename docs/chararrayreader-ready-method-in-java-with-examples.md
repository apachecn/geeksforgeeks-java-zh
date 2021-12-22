# Java 中的 CharArrayReader ready()方法，示例

> 原文:[https://www . geeksforgeeks . org/chararrayreader-ready-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chararrayreader-ready-method-in-java-with-examples/)

Java 中 **[CharArrayReader](https://www.geeksforgeeks.org/java-io-chararrayreader-class-java/)** 类的 **ready()** 方法用来检查这个 CharArrayReader 是否准备好被读取。它返回一个布尔值，表示读取器是否准备好了。

**语法:**

```java
public void ready()
```

**参数:**该方法不接受任何参数

**返回值:**该方法返回一个**布尔值**，该值告诉 CharArrayReader 是否准备好被读取。如果它准备好了，它就会变成真的。否则返回假。

**异常:**如果输入输出时出现错误，该方法抛出**异常**。

下面的方法说明了 ready()方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// CharArrayReader ready() method

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

            // Check if the CharArrayReader is
            // ready to be read using ready()
            System.out.println("Is CharArrayReader ready "
                               + "to be read: "
                               + reader.ready());

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
Is CharArrayReader ready to be read: true

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
// CharArrayReader ready() method

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

            reader.close();

            // Check if the CharArrayReader is
            // ready to be read using ready()
            System.out.println("Is CharArrayReader ready "
                               + "to be read: "
                               + reader.ready());

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
java.io.IOException: Stream closed

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/io/chararrayreader . html # ready–](https://docs.oracle.com/javase/9/docs/api/java/io/CharArrayReader.html#ready--)