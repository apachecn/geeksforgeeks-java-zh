# Java 中 CharArrayReader reset()方法，示例

> 原文:[https://www . geeksforgeeks . org/chararrayreader-reset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chararrayreader-reset-method-in-java-with-examples/)

Java 中 **[CharArrayReader](https://www.geeksforgeeks.org/java-io-chararrayreader-class-java/)** 类的 **reset()** 方法用于重置流。重置后，如果流已被标记，则此方法尝试在标记处重新定位它，否则它将尝试将其定位到起点。

**语法:**

```java
public void reset()
```

**参数:**该方法不接受任何参数。

**返回值:**此方法不返回值。

**异常:**如果输入输出时出现错误

*   If the stream is not marked*   If the tag is invalid*   If the reset () method is not supported, this method throws IOException:
    *   。

下面的方法说明了 reset()方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// CharArrayReader reset() method

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

            // Read the first 10 characters
            // to this reader using read() method
            // This will put the str in the stream
            // till it is read by the reader
            for (int i = 0; i < 10; i++) {
                ch = reader.read();
                System.out.print((char)ch);
            }

            System.out.println();

            // mark the stream for
            // 5 characters using reset()
            reader.mark(5);

            // reset the stream position
            reader.reset();

            // Read the 5 characters from marked position
            // to this reader using read() method
            for (int i = 0; i < 5; i++) {
                ch = reader.read();
                System.out.print((char)ch);
            }
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
GeeksForGe
eks??

```

**程序二:**

```java
// Java program to demonstrate
// CharArrayReader reset() method

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

            // Read the first 10 characters
            // to this reader using read() method
            // This will put the str in the stream
            // till it is read by the reader
            for (int i = 0; i < 10; i++) {
                ch = reader.read();
                System.out.print((char)ch);
            }

            System.out.println();

            // reset the stream position
            reader.reset();

            // Read the 5 characters from marked position
            // to this reader using read() method
            for (int i = 0; i < 5; i++) {
                ch = reader.read();
                System.out.print((char)ch);
            }
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
GeeksForGe
Geeks

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/io/chararrayreader . html # reset–](https://docs.oracle.com/javase/9/docs/api/java/io/CharArrayReader.html#reset--)