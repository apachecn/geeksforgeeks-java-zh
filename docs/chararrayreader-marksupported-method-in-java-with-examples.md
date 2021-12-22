# Java 中 CharArrayReader markSupported()方法，示例

> 原文:[https://www . geeksforgeeks . org/chararrayreader-marksupported-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chararrayreader-marksupported-method-in-java-with-examples/)

Java 中 **[CharArrayReader](https://www.geeksforgeeks.org/java-io-chararrayreader-class-java/)** 类的 **markSupported()** 方法用来检查这个 CharArrayReader 是否支持 mark()操作。它返回一个布尔值，该值表示读取器是否被标记为受支持。

**语法:**

```java
public boolean markSupported()
```

**参数:**该方法不接受任何参数

**返回值:**这个方法返回一个**布尔值**，告诉这个 CharArrayReader 是否支持 mark()操作。如果它是 markSupported，则返回 true。否则返回假。

下面的方法说明了 markSupported()方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// CharArrayReader markSupported() method

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
            // markSupported using markSupported()
            System.out.println("Is CharArrayReader markSupported: "
                               + reader.markSupported());

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
Is CharArrayReader markSupported: true

```

**程序二:**

```java
// Java program to demonstrate
// CharArrayReader markSupported() method

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        try {
            char[] str = { 'G', 'E', 'E', 'K', 'S' };

            // Create a CharArrayReader instance
            CharArrayReader reader
                = new CharArrayReader(str);

            // Check if the CharArrayReader is
            // markSupported using markSupported()
            System.out.println("Is CharArrayReader markSupported: "
                               + reader.markSupported());

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
Is CharArrayReader markSupported: true

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/io/chararrayreader . html # markSupported–](https://docs.oracle.com/javase/9/docs/api/java/io/CharArrayReader.html#markSupported--)