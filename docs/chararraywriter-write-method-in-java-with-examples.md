# 用 Java 编写 CharArrayWriter()方法，示例

> 原文:[https://www . geeksforgeeks . org/chararraywriter-write-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chararraywriter-write-method-in-java-with-examples/)

Java 中 **CharArrayWriter** 类的 **write()** 方法有三种类型:

1.  The **write(int)** method of **CharArrayWriter** class in Java is used to write a character to the writer in form of an integer. This write() method writes one character at a time to the CharArrayWriter.
    **Syntax:** 

    ```java
    public void write(int c)

    ```

    **覆盖:**该方法覆盖 **Writer** 类的 write()方法。
    **参数:**该方法接受一个参数 **c** ，代表要写入的整数。
    **返回值:**此方法不返回值。
    **异常:**此方法不抛出任何异常。
    下面的程序说明了 IO 包中 CharArrayWriter 类的 write(int)方法:
    **程序:**

    ## Java 语言(一种计算机语言，尤用于创建网站)

    ```java
    // Java program to illustrate
    // CharArrayWriter write(int) method

    import java.io.*;

    public class GFG {
        public static void main(String[] args)
        {

            // Create charArrayWriter
            CharArrayWriter charArrayWriter
                = new CharArrayWriter();

            // Write the character
            charArrayWriter.write(71);

            charArrayWriter.write(69);

            charArrayWriter.write(69);

            charArrayWriter.write(75);

            charArrayWriter.write(83);

            // print the charArrayWriter
            System.out.println(
                charArrayWriter.toString());
        }
    }
    ```

    **Output:**

    ```java
    GEEKS

    ```