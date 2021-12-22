# Java 中的 Java.io.Printstream 类|集合 1

> 原文:[https://www . geesforgeks . org/Java-io-print stream-class-Java-set-1/](https://www.geeksforgeeks.org/java-io-printstream-class-java-set-1/)

打印流为另一个输出流增加了功能，即方便地打印各种数据值的表示的能力。与其他输出流不同，打印流从不抛出 IOException 相反，异常情况只是设置了一个内部标志，可以通过 checkError 方法进行测试。或者，可以创建一个打印流来自动刷新。
打印流打印的所有字符都使用平台的默认字符编码转换为字节。PrintWriter 类应该在需要写入字符而不是字节的情况下使用。

**类申报**

```java
public class PrintStream
  extends FilterOutputStream
    implements Appendable, Closeable
```

**场**

```java
 protected OutputStream out:This is the output stream to be filtered. 
```

**施工人员及说明** 

*   **打印流(文件文件):**使用指定的文件创建新的打印流，无需自动刷新行。
*   **打印流(文件文件，字符串 csn) :** 使用指定的文件和字符集创建新的打印流，无需自动刷新行。
*   **打印流(输出流输出):**创建新的打印流。
*   **打印流(输出流输出，布尔自动刷新):**创建新的打印流。
*   **打印流(输出流输出，布尔自动刷新，字符串编码)**:创建新的打印流。
*   **打印流(字符串文件名):**使用指定的文件名创建新的打印流，无需自动刷新行。
*   **打印流(字符串文件名，字符串 csn) :** 使用指定的文件名和字符集创建新的打印流，无需自动刷新行。

**方法:**

*   **打印流追加(字符 c) :** 将指定的字符追加到该输出流。

    ```java
    Syntax :public PrintStream append(char c)
    Parameters: c - The 16-bit character to append
    Returns: This output stream
    ```

*   **打印流追加(CharSequence csq，int start，int end):** 向该输出流追加指定的字符序列。

    ```java
    Syntax :public PrintStream append(CharSequence csq,
                     int start,
                     int end)
    Parameters:
    csq - The character sequence from which a subsequence will be appended. 
    start - The index of the first character in the subsequence
    end - The index of the character following the last character in the subsequence
    Returns:
    This output stream
    Throws:
    IndexOutOfBoundsException
    ```

*   **打印流追加(CharSequence csq) :** 向该输出流追加指定字符序列的子序列。

    ```java
    Syntax :public PrintStream append(CharSequence csq)
    Parameters:
    csq - The character sequence to append. 
    Returns:
    This output stream

    ```

*   **布尔检查器错误():**刷新流并检查其错误状态。

    ```java
    Syntax :public boolean checkError()
    Returns:
    true if and only if this stream has encountered an IOException 
    other than InterruptedIOException, or the setError method has been invoked
    ```

*   **受保护的 void clearError() :** 清除此流的内部错误状态。

    ```java
    Syntax :protected void clearError()

    ```

*   **虚空关闭():**关闭溪流。

    ```java
    Syntax :public void close()
    Overrides: close in class FilterOutputStream
    ```

*   **虚空冲():**冲溪。

    ```java
    Syntax :public void flush()
    Overrides: flush in class FilterOutputStream
    ```

*   **打印流格式(Locale l，String 格式，Object… args):** 使用指定的格式字符串和参数将格式化的字符串写入该输出流。

    ```java
    Syntax :public PrintStream format(Locale l,
                     String format,
                     Object... args)
    Parameters:
    l - The locale to apply during formatting. 
    If l is null then no localization is applied.
    format - A format string as described in Format string syntax
    args - Arguments referenced by the format specifiers in the format string. 
    The number of arguments is variable and may be zero.
    Returns: This output stream
    Throws:
    IllegalFormatException 
    NullPointerException
    ```

*   **打印流格式(字符串格式，对象…参数):**使用指定的格式字符串和参数将格式化的字符串写入该输出流。

    ```java
    Syntax :public PrintStream format(String format,
                     Object... args)
    Parameters:
    format - A format string as described in Format string syntax
    args - Arguments referenced by the format specifiers in the format string. 
    The number of arguments is variable and may be zero.
    Returns:
    This output stream
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

```java
import java.io.FileNotFoundException;
import java.io.FileOutputStream;
import java.io.PrintStream;
import java.util.Locale;
//Java program to demonstrate PrintStream methods
class Printstream
{
    public static void main(String args[]) throws FileNotFoundException
    {
        FileOutputStream fout=new FileOutputStream("file.txt");

        //creating Printstream obj
        PrintStream out=new PrintStream(fout);
        String s="First";

        //writing to file.txt
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
        out.print(fout);
        out.println();

        //illustrating append(CharSequence csq) method
        out.append("Geek");
        out.println();

        //illustrating checkError() method
        out.println(out.checkError());

        //illustrating format() method
        out.format(Locale.UK, "Welcome to my %s program", s);

        //illustrating flush method
        out.flush();

        //illustrating close method
        out.close();
    }
}
```

注意:输出可能在联机集成开发环境中不可见，因为它无法读取文件。
**输出:**

```java
true14.533GeeksforGeeks
java.io.FileOutputStream@1540e19dGeek
false
Welcome to my First program
```

**下一篇:** [Java 中的 Java.io.Printstream 类|第二集](https://www.geeksforgeeks.org/java-io-printstream-class-java-set-2/)

本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766?ref=bookmarks)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。