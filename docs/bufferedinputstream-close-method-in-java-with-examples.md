# Java 中的 BufferedInputStream close()方法，示例

> 原文:[https://www . geeksforgeeks . org/bufferedinputstream-close-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bufferedinputstream-close-method-in-java-with-examples/)

Java 中 **BufferedInputStream** 类的 **close()** 方法关闭输入流并释放与之相关的任何系统资源。一旦调用 close()方法，读取任何输入文件都将被禁止，系统将抛出一个 IOException。为了解决这个问题，用户可以使用 try-catch 块来捕获任何这样的异常并抛出一个正确的指令。

**语法:**

```
public void close()

```

**参数:**此方法不接受任何参数。

**返回值:**此方法不返回值。

**覆盖:**该方法被*在类**中关闭***所覆盖 [FilterInputStream](https://www.geeksforgeeks.org/java-io-filterinputstream-class-in-java/) 。

**异常:**如果出现输入输出错误，该方法抛出 **IOException** 。

下面的程序说明了 IO 包中 BufferedInputStream 类的 close()方法:

**程序 1:** 假设文件“c:/demo.txt”存在。

```
// Java program to illustrate
// BufferedInputStream.close() method

import java.io.*;
public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // Create input stream 'demo.txt'
        // for reading containing
        // text "GEEKSFORGEEKS"
        FileInputStream inputStream
            = new FileInputStream("c:/demo.txt");

        // Convert inputStream to
        // bufferedInputStream
        BufferedInputStream buffInputStr
            = new BufferedInputStream(inputStream);

        // Get the number of bytes available
        // to read using available() method
        int rem_byte = buffInputStr.available();

        // Number of bytes available is printed
        System.out.println(
            "Remaining Byte: " + rem_byte);

        // Close the file
        buffInputStr.close();
    }
}
```

**输出:**

```
Remaining Byte: 13

```

**程序二:**假设文件“c:/demo.txt”存在。

```
// Java program to illustrate
// BufferedInputStream.close() method

import java.io.*;
public class GFG {
    public static void main(String[] args)
        throws IOException
    {
        try {

            // create input stream 'demo.txt'
            // for reading containing
            // text "GEEKS"
            FileInputStream inputStream
                = new FileInputStream(
                    "c:/demo.txt");

            // convert inputStream to
            // bufferedInputStream
            BufferedInputStream buffInputStr
                = new BufferedInputStream(
                    inputStream);

            // get the number of bytes available
            // to read using available() method
            int rem_byte
                = buffInputStr.available();

            // number of bytes available is printed
            System.out.println(rem_byte);

            // close the file
            buffInputStr.close();

            // now throws io exception
            // if available() is invoked
            // after close()
            rem_byte = buffInputStr.available();

            System.out.println(rem_byte);
        }
        catch (IOException e) {
            // exception occurred.
            System.out.println(
                "Error: Sorry 'buffInputStr'"
                + " is closed");
        }
    }
}
```

**输出:**

```
5
Error: Sorry 'buffInputStr' is closed

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/io/bufferedinputstream . html # close()](https://docs.oracle.com/javase/10/docs/api/java/io/BufferedInputStream.html#close())