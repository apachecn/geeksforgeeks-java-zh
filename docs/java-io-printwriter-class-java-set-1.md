# Java 中的 Java.io.PrintWriter 类|集合 1

> 原文:[https://www . geesforgeks . org/Java-io-print writer-class-Java-set-1/](https://www.geeksforgeeks.org/java-io-printwriter-class-java-set-1/)

这个类将对象的打印格式表示提供给文本输出流。它实现了 PrintStream 中的所有打印方法。它不包含写入原始字节的方法，程序应该使用未编码的字节流。
与 PrintStream 类不同的是，如果启用了自动刷新，它将仅在调用 println、printf 或 format 方法之一时进行，而不是在输出换行符时进行。这些方法使用平台自己的行分隔符概念，而不是换行符。

这个类中的方法从不抛出输入输出异常，尽管它的一些构造函数可能会抛出。客户端可以通过调用 checkError()来查询是否发生了任何错误。
 **建造师及说明**

*   **PrintWriter(文件文件):**使用指定的文件创建一个新的 PrintWriter，无需自动刷新行。
*   **PrintWriter(文件文件，字符串 csn) :** 使用指定的文件和字符集创建一个新的 PrintWriter，无需自动刷新行。
*   **打印编写器(输出流输出):**从现有输出流创建一个新的打印编写器，无需自动刷新行。
*   **打印编写器(输出流输出，布尔自动刷新):**从现有输出流创建新的打印编写器。
*   **PrintWriter(字符串文件名):**使用指定的文件名创建一个新的 PrintWriter，无需自动刷新行。
*   **PrintWriter(String fileName，String csn) :** 使用指定的文件名和字符集创建一个新的 PrintWriter，无需自动刷新行。
*   **PrintWriter(Writer out):** 创建新的 PrintWriter，不自动刷新行。
*   **PrintWriter(Writer out，布尔自动刷新):**创建一个新的 PrintWriter。

**方法:**

*   **PrintWriter 追加(char c) :** 向该 Writer 追加指定字符

    ```java
    Syntax :public PrintWriter append(char c)
    Parameters: c - The 16-bit character to append
    Returns: This writer
    ```

*   **PrintWriter 追加(CharSequence csq，int start，int end):** 向该 Writer 追加指定的字符序列。

    ```java
    Syntax :public PrintWriter append(CharSequence csq,
            int start,
            int end)
    Parameters:
            csq - The character sequence from which a subsequence will be appended.
            start - The index of the first character in the subsequence
            end - The index of the character following the last character in the subsequence
    Returns:This writer
    Throws:
            IndexOutOfBoundsException
    ```

*   **print Writer append(CharSequence csq):**将指定字符序列的子序列附加到此 writer。

    ```java
    Syntax :public PrintWriter append(CharSequence csq)
    Parameters:
            csq - The character sequence to append.
    Returns: This writer

    ```

*   **布尔检查器错误():**刷新流并检查其错误状态。

    ```java
    Syntax :public boolean checkError()
    Returns: true if and only if this stream 
    has encountered an IOException other than InterruptedIOException, 
    or the setError method has been invoked
    ```

*   **受保护的 void clearError() :** 清除此流的内部错误状态。

    ```java
    Syntax :protected void clearError()

    ```

*   **void close() :** 关闭流并释放与其相关联的任何系统资源。

    ```java
    Syntax :public void close()
    Specified by:close in class Writer
    ```

*   **虚空冲():**冲溪。

    ```java
    Syntax :public void flush()
    Specified by:flush in interface Flushable
    Specified by:flush in class Writer

    ```

*   **PrintWriter 格式(Locale l，String 格式，Object… args):** 使用指定的格式字符串和参数将格式化的字符串写入此 Writer。

    ```java
    Syntax :public PrintWriter format(Locale l,
            String format,
            Object... args)
    Parameters:
            l - The locale to apply during formatting. If l is null,
     then no localization is applied.
            format - A format string as described in Format string syntax
            args - Arguments referenced by the format specifiers in the format string. 
    The number of arguments is variable and may be zero.
    Returns: This writer
    Throws:
            IllegalFormatException
            NullPointerException
    ```

*   **PrintWriter 格式(字符串格式，Object… args):** 使用指定的格式字符串和参数将格式化的字符串写入此 Writer。

    ```java
    Syntax :public PrintWriter format(String format,
            Object... args)
    Parameters:
            format - A format string as described in Format string syntax
            args - Arguments referenced by the format specifiers in the format string. 
    The number of arguments is variable and may be zero.
    Returns: This writer
    Throws:
            IllegalFormatException
            NullPointerException 
    ```

*   **无效打印(布尔值 b):** 打印布尔值。

    ```java
    Syntax :public void print(boolean b)
    ```

*   **无效打印(字符 c):** 打印字符。

    ```java
    Syntax :public void print(char c)
    ```

*   **无效打印(字符[]):**打印字符数组。

    ```java
    Syntax :public void print(char[] s)

    ```

*   **空打印(双 d) :** 打印双精度浮点数。

    ```java
    Syntax :public void print(double b)

    ```

*   **void print(float f):** 打印浮点数。

    ```java
    Syntax :public void print(float f)
    ```

*   **无效打印(int i):** 打印整数。

    ```java
    Syntax :public void print(int i)
    ```

*   **无效打印(长 l):** 打印长整数。

    ```java
    Syntax :public void print(long l)
    ```

*   **无效打印(对象对象):**打印对象。

    ```java
    Syntax :public void print(Object obj)
    ```

*   **无效打印(字符串):**打印字符串。

    ```java
    Syntax :public void print(String s)
    ```

**节目:** 

```java
import java.io.*;
import java.util.Locale;
//Java program to demonstrate PrintWriter
class PrintWriterDemo {

    public static void main(String[] args) 
        {
        String s="GeeksforGeeks";

        // create a new writer
        PrintWriter out = new PrintWriter(System.out);
        char c[]={'G','E','E','K'};

        //illustrating print(boolean b) method
        out.print(true);

        //illustrating print(int i) method
        out.print(1);

        //illustrating print(float f) method
        out.print(4.533f);

        //illustrating print(String s) method
        out.print("GeeksforGeeks");
        out.println();

        //illustrating print(Object Obj) method
        out.print(out);
        out.println();

        //illustrating append(CharSequence csq) method
        out.append("Geek");
        out.println();

        //illustrating checkError() method
        out.println(out.checkError());

        //illustrating format() method
        out.format(Locale.UK, "This is my %s program", s);

        //illustrating flush method
        out.flush();

        //illustrating close method
        out.close();
    }
}
```

```java
Output:
        true14.533GeeksforGeeks
        java.io.PrintWriter@1540e19d
        Geek
        false
        This is my GeeksforGeeks program
```

**下一篇:** [Java.io.PrintWriter 类中的 Java | Set 2](https://www.geeksforgeeks.org/java-io-printwriter-class-java-set-2/)

本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766?ref=bookmarks)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。