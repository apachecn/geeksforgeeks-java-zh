# Java 中 CharArrayWriter size()方法示例

> 原文:[https://www . geeksforgeeks . org/chararraywriter-size-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chararraywriter-size-method-in-java-with-examples/)

Java 中 **CharArrayWriter** 类的 **size()** 方法用于获取缓冲区的当前大小。
**语法** :

```java
public int size()
```

**参数:**此方法不接受任何参数。
**返回值:**该方法返回一个*整数*值，表示缓冲区的当前大小。
以下程序举例说明上述方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate
// the size() method

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
    }
}
```

**Output:** 

```java
Size of char_array1 : 5
```

**节目 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate
// the size() method

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
    }
}
```

**Output:** 

```java
Size of char_array1 : 6
```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/io/chararraywriter . html # size()](https://docs.oracle.com/javase/10/docs/api/java/io/CharArrayWriter.html#size())T4】