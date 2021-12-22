# Java 中 CharArrayWriter toCharArray()方法，带示例

> 原文:[https://www . geeksforgeeks . org/chararraywriter-to chararray-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chararraywriter-tochararray-method-in-java-with-examples/)

Java 中 **CharArrayWriter** 类的 **toCharArray()** 方法返回输入数据的副本。

**语法** :

```java
public char[] toCharArray()
```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回输入数据的副本。

下面的程序说明了上面的方法:

**程序 1:**

```java
// Java program to illustrate
// the toCharArray() method

import java.io.*;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // Initializing String Witer
        CharArrayWriter geek_writer1
            = new CharArrayWriter();

        char[] Sw = { 'G', 'E', 'E', 'K', 'S' };

        for (char c : Sw) {

            // Use of append(char Sw) :
            geek_writer1.append(c);
        }

        // Use of toCharArray() :
        char[] toChar1 = geek_writer1.toCharArray();

        for (char c1 : toChar1) {
            System.out.println("toCharArray : " + c1);
        }
    }
}
```

**输出:**

```java
toCharArray : G
toCharArray : E
toCharArray : E
toCharArray : K
toCharArray : S

```

**程序二:**

```java
// Java program to illustrate
// the toCharArray() method

import java.io.*;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // Initializing String Witer
        CharArrayWriter geek_writer1
            = new CharArrayWriter();

        char[] Sw = { 'G', 'O', 'P', 'A',
                      'L', 'D', 'A', 'V', 'E' };

        for (char c : Sw) {
            // Use of append(char Sw) :
            geek_writer1.append(c);
        }

        // Use of toCharArray() :
        char[] toChar1 = geek_writer1.toCharArray();

        for (char c1 : toChar1) {
            System.out.println("toCharArray : " + c1);
        }
    }
}
```

**输出:**

```java
toCharArray : G
toCharArray : O
toCharArray : P
toCharArray : A
toCharArray : L
toCharArray : D
toCharArray : A
toCharArray : V
toCharArray : E

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/io/chararraywriter . html # toCharArray()](https://docs.oracle.com/javase/10/docs/api/java/io/CharArrayWriter.html#toCharArray())