# Java 中 CharArrayWriter reset()方法示例

> 原文:[https://www . geeksforgeeks . org/chararraywriter-reset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chararraywriter-reset-method-in-java-with-examples/)

Java 中 **CharArrayWriter** 类的 **reset()** 方法用于重置缓冲区，以便可以再次使用，而不会扔掉已经分配的缓冲区。
**语法** :

```
public void reset()
```

**参数:**此方法不接受任何参数。
**返回值:**这个方法不返回任何东西。
以下程序举例说明上述方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate
// the reset() method

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

        // Resets the current stream
        char_array1.reset();

        // Use of size() method
        System.out.println("Size of char_array1 : "
                           + char_array1.size());
    }
}
```

**Output:** 

```
Size of char_array1 : 5
Size of char_array1 : 0
```

**节目 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate
// the reset() method

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

        // Resets the current stream
        char_array1.reset();

        // Use of size() method
        System.out.println("Size of char_array1 : "
                           + char_array1.size());
    }
}
```

**Output:** 

```
Size of char_array1 : 6
Size of char_array1 : 0
```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/io/chararraywriter . html # reset()](https://docs.oracle.com/javase/10/docs/api/java/io/CharArrayWriter.html#reset())T4】