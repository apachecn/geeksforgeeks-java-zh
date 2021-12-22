# Java 中的 BufferedInputStream 标记()方法，示例

> 原文:[https://www . geeksforgeeks . org/bufferedinputstream-mark-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bufferedinputstream-mark-method-in-java-with-examples/)

Java 中 **BufferedInputStream** 类的**标记()**方法用于标记输入流中的当前位置。同一类的 Reset()方法 **BufferedInputStream** 在 mark()方法之后调用。Reset()将位置固定在最后标记的位置，以便可以再次读取相同的字节。

**一般约定:**输入流以某种方式保存调用 mark()方法后读取的所有字节，并在调用 reset()方法时再次返回相同的字节。只有当 markSupported()返回 true 时，才会执行此操作。但是，如果在调用 reset()方法之前读取的字节数大于 readlimit 字节数，则输入流不需要保存任何数据。

**语法:**

```
public void mark(int readlimit)

```

**覆盖:**覆盖 **FilterInputStream** 类的 mark()方法。

**参数:**该方法接受整数类型的一个参数**读限制**，该参数表示在标记位置无效之前可以读取的字节的最大限制。

**返回值:**此方法不返回值。

**异常:**此方法不抛出任何异常。

下面的程序说明了 IO 包中 BufferedInputStream 类中的 mark()方法:
**程序 1:** 假设文件“c:/demo.txt”的存在。

```
// Java program to illustrate
// BufferedInputStream mark() method

import java.io.*;

public class GFG {
    public static void main(String[] args)
    {

        // Create input stream 'demo.txt'
        // for reading containing text "GEEKS"
        FileInputStream inputStream
            = new FileInputStream(
                "c:/demo.txt");

        // Convert inputStream to
        // bufferedInputStream
        BufferedInputStream buffInputStr
            = new BufferedInputStream(
                inputStream);

        // Read and print characters one by one
        System.out.println(
            "Char : "
            + (char)buffInputStr.read());
        System.out.println(
            "Char : "
            + (char)buffInputStr.read());
        System.out.println(
            "Char : "
            + (char)buffInputStr.read());

        // Mark is set on the input stream
        buffInputStr.mark(0);

        System.out.println(
            "Char : "
            + (char)buffInputStr.read());

        // Reset() is invoked
        buffInputStr.reset();

        // Read and print characters
        System.out.println(
            "Char : "
            + (char)buffInputStr.read());
        System.out.println(
            "Char : "
            + (char)buffInputStr.read());
    }
}
```

**Output:**

```
Char : G
Char : E
Char : E
Char : K
Char : K
Char : S

```

**程序 2:** 假设存在文件“c:/demo.txt”。

```
// Java program to illustrate
// BufferedInputStream.mark() method
import java.io.*;
public class GFG {
    public static void main(String[] args)
    {

        // Create input stream 'demo.txt'
        // for reading containing text
        // "GEEKSFORGEEKS"
        FileInputStream inputStream
            = new FileInputStream(
                "c:/demo.txt");

        // Convert inputStream to
        // bufferedInputStream
        BufferedInputStream buffInputStr
            = new BufferedInputStream(
                inputStream);

        // Read and print characters one by one
        System.out.println(
            "Char : "
            + (char)buffInputStr.read());
        System.out.println(
            "Char : "
            + (char)buffInputStr.read());
        System.out.println(
            "Char : "
            + (char)buffInputStr.read());
        System.out.println(
            "Char : "
            + (char)buffInputStr.read());

        // Mark is set on the input stream
        buffInputStr.mark(0);

        System.out.println(
            "Char : "
            + (char)buffInputStr.read());

        // Reset() is invoked
        buffInputStr.reset();

        // read and print characters
        System.out.println(
            "Char : "
            + (char)buffInputStr.read());
        System.out.println(
            "Char : "
            + (char)buffInputStr.read());
        System.out.println(
            "Char : "
            + (char)buffInputStr.read());
        System.out.println(
            "Char : "
            + (char)buffInputStr.read());
    }
}
```

**Output:**

```
Char : G
Char : E
Char : E
Char : K
Char : S
Char : S
Char : F
Char : O
Char : R

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/io/bufferedinputstream . html # mark(int)](https://docs.oracle.com/javase/10/docs/api/java/io/BufferedInputStream.html#mark(int))