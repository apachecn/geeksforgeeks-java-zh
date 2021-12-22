# Java 中 CharArrayReader close()方法，带示例

> 原文:[https://www . geeksforgeeks . org/chararrayreader-close-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chararrayreader-close-method-in-java-with-examples/)

Java 中 **[CharArrayReader](https://www.geeksforgeeks.org/java-io-chararrayreader-class-java/)** 类的 **close()** 方法用于关闭流并释放流中繁忙的资源(如果有)。该方法有以下结果:

*   If the stream is open, close the stream to release resources.
*   If the stream has been closed, it has no effect.
*   If the stream performs any reading or other similar operations, it will throw IOException when it is closed.

**语法:**

```
public abstract void close()
```

**参数:**该方法不接受任何参数

**返回值:**此方法不返回值。

**异常:**如果在输入输出时出现一些错误，这个方法抛出 IOException。

下面的方法说明了 close()方法的工作原理:

**程序 1:**

```
// Java program to demonstrate
// CharArrayReader close() method

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

            // Close the stream using close()
            reader.close();
            System.out.println("Stream Closed.");
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
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
Stream Closed.

```

**程序二:**

```
// Java program to demonstrate
// CharArrayReader close() method

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            char[] str = { 'G', 'e', 'e', 'k', 's' };

            // Create a CharArrayReader instance
            CharArrayReader reader
                = new CharArrayReader(str);

            // Close the stream using close()
            reader.close();
            System.out.println("Stream Closed.");

            // Check if the CharArrayReader is
            // ready to be read using ready()
            System.out.println("Is CharArrayReader ready "
                               + "to be read"
                               + reader.ready());
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
Stream Closed.
java.io.IOException: Stream closed

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/io/chararrayreader . html # close–](https://docs.oracle.com/javase/9/docs/api/java/io/CharArrayReader.html#close--)