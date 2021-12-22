# Java 中 CharArrayWriter append()方法示例

> 原文:[https://www . geeksforgeeks . org/chararraywriter-append-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chararraywriter-append-method-in-java-with-examples/)

Java 中 **CharArrayWriter** 类的 **append()** 方法有三种类型:

1.  The **append(char)** method of **CharArrayWriter** class in Java is used to append the specified character to the writer. This append() method appends one character at a time to the CharArrayWriter and returns this CharArrayWriter.
    **Syntax:** 

    ```
    public CharArrayWriter append(char c)

    ```

    **指定者:**该方法由**可追加**界面的 append()方法指定。
    **覆盖:**该方法覆盖 **Writer** 类的 append()方法。
    **参数:**该方法接受一个参数 **c** ，表示要追加的 16 位字符。
    **返回值:**该方法在追加字符后返回 **CharArrayWriter** 。
    **异常:**这个方法不抛出任何异常。
    下面的程序说明了 IO 包中 CharArrayWriter 类中的 append(char)方法:
    **程序:**

    ## Java 语言(一种计算机语言，尤用于创建网站)

    ```
    // Java program to illustrate
    // CharArrayWriter append(char) method

    import java.io.*;

    public class GFG {
        public static void main(String[] args)
        {

            // Create charArrayWriter
            CharArrayWriter charArrayWriter
                = new CharArrayWriter();

            // Append the character
            charArrayWriter.append('G');

            charArrayWriter.append('E');

            charArrayWriter.append('E');

            charArrayWriter.append('K');

            charArrayWriter.append('S');

            // print the charArrayWriter
            System.out.println(
                charArrayWriter.toString());
        }
    }
    ```

    **Output:**

    ```
    GEEKS

    ```