# CharArrayReader 用示例读取 Java 中的(char[])方法

> 原文:[https://www . geeksforgeeks . org/chararrayreader-readchar-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chararrayreader-readchar-method-in-java-with-examples/)

Java 中 **[CharArrayReader](https://www.geeksforgeeks.org/java-io-chararrayreader-class-java/)** 类的 **read(char[])** 方法用于将指定的字符读入数组。这个方法阻塞流直到:

*   It takes some input from the stream.
*   Some IOException occurred.
*   It has reached the end of the stream when reading.

**语法:**

```
public int read(char[] charArray)
```

**参数:**该方法接受一个强制参数**字符数组**，它是要写入流中的字符数组。

**返回值:**该方法返回一个**整数值**，即从流中读取的字符数。如果未读取任何字符，则返回-1。

**异常:**如果输入输出时出现错误，该方法抛出**异常**。

下面的方法说明了 read(char[])方法的工作原理:

**程序 1:**

```
// Java program to demonstrate
// CharArrayReader read(char[]) method

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

            // Get the character array
            // to be read from the stream
            char[] charArray = new char[5];

            // Read the charArray
            // to this reader using read() method
            // This will put the str in the stream
            // till it is read by the reader
            reader.read(charArray);

            // Print the read charArray
            System.out.println(
                Arrays
                    .toString(charArray));

            reader.close();
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
[G, e, e, k, s]

```

**程序二:**

```
// Java program to demonstrate
// CharArrayReader read(char[]) method

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

            // Get the character array
            // to be read from the stream
            char[] charArray
                = new char[13];

            // Read the charArray
            // to this reader using read() method
            // This will put the str in the stream
            // till it is read by the reader
            reader.read(charArray);

            // Print the read charArray
            System.out.println(
                Arrays
                    .toString(charArray));

            reader.close();
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
[G, e, e, k, s, F, o, r, G, e, e, k, s]

```

**参考:**