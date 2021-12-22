# Java 中 CharArrayWriter toString()方法，带示例

> 原文:[https://www . geeksforgeeks . org/chararraywriter-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chararraywriter-tostring-method-in-java-with-examples/)

Java 中 **CharArrayWriter** 类的 **toString()** 方法将给定的输入数据转换为字符串。

**语法**:

```java
public String[] toString()
```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回输入数据的副本。

下面的程序说明了上面的方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate the
// above mentioned method

import java.io.*;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // Initializing String Witer
        CharArrayWriter geek_writer1
            = new CharArrayWriter();

        CharSequence char_sq1 = "geeks for + ";
        CharSequence char_sq2 = "geeks";

        // Use of append(CharSequence char_sq)
        geek_writer1.append(char_sq1);
        geek_writer1.append(char_sq2);

        // Convert it into string and print
        System.out.println("String : "
                           + geek_writer1.toString());
    }
}
```

**Output:** 

```java
String : geeks for + geeks
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate the
// above mentioned method

import java.io.*;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // Initializing String Witer
        CharArrayWriter geek_writer1
            = new CharArrayWriter();

        CharSequence char_sq1 = "Gopal ";
        CharSequence char_sq2 = "Dave";

        // Use of append(CharSequence char_sq)
        geek_writer1.append(char_sq1);
        geek_writer1.append(char_sq2);

        // Convert it into string and print
        System.out.println("String : "
                           + geek_writer1.toString());
    }
}
```

**Output:** 

```java
String : Gopal Dave
```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/io/chararraywriter . html # toString()](https://docs.oracle.com/javase/10/docs/api/java/io/CharArrayWriter.html#toString())