# Java 中 CharArrayWriter flush()方法，带示例

> 原文:[https://www . geeksforgeeks . org/chararraywriter-flush-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chararraywriter-flush-method-in-java-with-examples/)

Java 中 **CharArrayWriter** 类的 **flush()** 方法用于刷新流。
**语法** :

```
public void flush()
```

**参数:**此方法不接受任何参数。
**返回值:**这个方法不返回任何东西。
以下程序举例说明上述方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate
// the flush() method

import java.io.*;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // Initializing the character array
        char[] geek = { 'G', 'E', 'E', 'K', 'S' };

        // Initializing the CharArrayWriter
        CharArrayWriter char_array1
            = new CharArrayWriter();

        for (int c = 72; c < 77; c++) {
            // Use of write(int char)
            // Writer int value to the Writer
            char_array1.write(c);
        }

        // Use of size() method
        System.out.println("\nSize of char_array1 : "
                           + char_array1.size());

        // Flushes the current stream
        char_array1.flush();
    }
}
```

**Output:** 

```
Size of char_array1 : 5
```

**节目 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate
// the flush() method

import java.io.*;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // Initializing the character array
        char[] geek
            = { 'G', 'O', 'P', 'A', 'L', 'L' };

        // Initializing the CharArrayWriter
        CharArrayWriter char_array1
            = new CharArrayWriter();

        for (int c = 72; c < 78; c++) {
            // Use of write(int char)
            // Writer int value to the Writer
            char_array1.write(c);
        }

        // Use of size() method
        System.out.println("\nSize of char_array1 : "
                           + char_array1.size());

        // Flushes the current stream
        char_array1.flush();
    }
}
```

**Output:** 

```
Size of char_array1 : 6
```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/io/chararraywriter . html # flush()](https://docs.oracle.com/javase/10/docs/api/java/io/CharArrayWriter.html#flush())T4】