# Java 中的 Java.io.Printstream 类|第 2 集

> 原文:[https://www . geesforgeks . org/Java-io-print stream-class-Java-set-2/](https://www.geeksforgeeks.org/java-io-printstream-class-java-set-2/)

[Java 中的 Java.io.Printstream 类|集 1](https://www.geeksforgeeks.org/java-io-printstream-class-java-set-1/)
**更多方法:**

*   **PrintStream printf(Locale l，String format，Object… args) :** 一种使用指定的格式字符串和参数将格式化字符串写入该输出流的便捷方法。

    ```java
    Syntax :public PrintStream printf(Locale l,
                     String format,
                     Object... args)
    Parameters: l - The locale to apply during formatting. If l is null then no localization is applied.
    format - A format string as described in Format string syntax
    args - Arguments referenced by the format specifiers in the format string.
    Returns:
    This output stream
    Throws:
    IllegalFormatException 
    NullPointerException
    ```

    ```java
    //Java program to demonstrate printf method
    import java.io.*;
    import java.util.Locale;

    class PrintStreamDemo 
    {
        public static void main(String[] args) 
        {
            String s = "for";

            // create printstream object
            PrintStream printStream = new PrintStream(System.out);

            // illustrating printf(Locale l, String format, Object... args) method
            printStream.printf(Locale.US, "Geeks%sGeeks", s);
        }
    }
    ```

    ```java
    Output:
    GeeksforGeeks
    ```

*   **PrintStream printf(String format，Object… args) :** 一种使用指定的格式字符串和参数将格式化字符串写入该输出流的便捷方法。

    ```java
    Syntax :public PrintStream printf(String format,
                     Object... args)
    Parameters:
    format - A format string as described in Format string syntax
    args - Arguments referenced by the format specifiers in the format string.
    Returns:
    This output stream
    Throws:
    IllegalFormatException 
    NullPointerException 
    ```

    ```java
    //Java program to demonstrate printf(String format, Object... args) method
    import java.io.*;

    public class PrintStreamDemo 
    {
        public static void main(String[] args)
        {
            String s = "for";

            // create printstream object
            PrintStream obj= new PrintStream(System.out);

            // illustrating printf(String format, Object... args) method
            obj.printf("Geeks%sGeeks", s);
        }
    }
    ```

    ```java
    Output:
    GeeksforGeeks
    ```

*   **void println():** 通过写入行分隔符字符串终止当前行。

    ```java
    Syntax :public void println()
    ```

    ```java
    //Java program to demonstrate println() methods
    import java.io.PrintStream;

    class PrintStreamDemo
    {
        public static void main(String[] args)
        {
            PrintStream obj = new PrintStream(System.out);

            //illustrating println();
            obj.println("GeeksforGeeks");
        }
    }
    ```

    ```java
    Output:
    GeeksforGeeks
    ```

*   **void println(布尔值 x):** 打印一个布尔值，然后终止该行。

    ```java
    Syntax :public void println(boolean x)
    ```

    ```java
    //Java program to demonstrate println(boolean) method
    import java.io.*;

    class PrintStreamDemo 
    {
        public static void main(String[] args) 
        {
            // create printstream object
            PrintStream obj = new PrintStream(System.out);

            //illustrating println(boolean) method
            obj.println(true);

            // flush the stream
            obj.flush();
        }
    }
    ```

    ```java
    Output:
    true
    ```

*   **void println(char x):** 打印一个字符，然后结束该行。

    ```java
    Syntax :public void println(char x)
    ```

    ```java
    //Java program to demonstrate println(char x) method
    import java.io.*;

    public class PrintStreamDemo 
    {
        public static void main(String[] args) 
        {
            char c = 'g';

            // create printstream object
            PrintStream obj = new PrintStream(System.out);

            // illustrating println(char x)
            obj.println(c);

            // flush the stream
            obj.flush();

        }
    }
    ```

    ```java
    Output:
    g
    ```

*   **void println(char[] x):** 打印一个字符数组，然后结束该行。

    ```java
    Syntax :public void println(char[] x)
    ```

    ```java
    //Java program to demonstrate println(char[] x) method
    import java.io.*;

    public class PrintStreamDemo 
    {
        public static void main(String[] args) 
        {
            char[] c = {'G', 'E', 'E','K'};

            // create printstream object
            PrintStream obj = new PrintStream(System.out);

            // illustrating println(char[] x)
            obj.println(c);

            // flush the stream
            obj.flush();
        }
    }
    ```

    ```java
    Output:
    GEEK

    ```

*   **void println(double x):** Prints a double and then terminate the line.

    ```java
    Syntax :public void println(double x)
    ```

    ```java
    //Java program to demonstrate println(double x) method
    import java.io.*;

    public class PrintStreamDemo
    {
        public static void main(String[] args) 
        {
            double c = 5.42762;

            // create printstream object
            PrintStream obj = new PrintStream(System.out);

            // illustrating println(double x)
            obj.println(c);

            // flush the stream
            obj.flush();
        }
    }
    ```

    **输出:**

    ```java
    5.42762
    ```

*   **void println(float x):** Prints a float and then terminate the line.

    ```java
    Syntax :public void println(float x)
    ```

    ```java
    //Java program to demonstrate println(float x) method
    import java.io.*;
    public class PrintStreamDemo
    {
        public static void main(String[] args) 
        {
            float c = 5.168502f;

            // create printstream object
            PrintStream obj = new PrintStream(System.out);

            // illustrating println(float x)
            obj.println(c);

            // flush the stream
            obj.flush();
        }
    }
    ```

    **输出:**

    ```java
    5.168502f
    ```

*   **void println(int x):** Prints an integer and then terminate the line.

    ```java
    Syntax :public void println(boolean x)
    ```

    ```java
    //Java program to demonstrate println(int x) method
    import java.io.*;

    public class PrintStreamDemo
    {
        public static void main(String[] args)
        {

            int c = 5;

            // create printstream object
            PrintStream obj = new PrintStream(System.out);

            // illustrating println(int x)
            obj.println(c);

            // flush the stream
            obj.flush();
        }
    }
    ```

    **输出:**

    ```java
    5

    ```

*   **void println(long x):** Prints a long and then terminate the line.

    ```java
    Syntax :public void println(long x)
    ```

    ```java
    //Java program to demonstrate println(long x) method

    import java.io.*;
    public class PrintStreamDemo 
    {
        public static void main(String[] args)
        {
            long c = 123456789l;
            try 
            {
                // create printstream object
                PrintStream obj= new PrintStream(System.out);

                // illustrating println(long x)
                obj.println(c);

                // flush the stream
                obj.flush();
            }
            catch (Exception ex)
            {
                ex.printStackTrace();
            }
        }
    }
    ```

    **输出:**

    ```java
    123456789
    ```

*   **void println(Object x) :**Prints an Object and then terminate the line.

    ```java
    Syntax :public void println(Object x)
    ```

    ```java
    //Java program to demonstrate println(Object x) method
    import java.io.*;

    public class PrintStreamDemo 
    {

        public static void main(String[] args) 
        {
            // create printstream object
            PrintStream obj = new PrintStream(System.out);

            //illustrating println(Object X)
            obj.println(obj);

            // flush the stream
            obj.flush();
        }
    }
    ```

    **输出:**

    ```java
    java.io.PrintStream@15db9742
    ```

*   **void println(String x) :**Prints a String and then terminate the line.

    ```java
    Syntax :public void println(boolean x)
    ```

    ```java
    import java.io.*;
    import java.io.*;
    //Java program to demonstrate println(String x) method
    public class PrintStreamDemo 
    {
        public static void main(String[] args) 
        {
            String c = "GeeksforGeeks";

            // create printstream object
            PrintStream ps = new PrintStream(System.out);

            // illustrating println(String x)
            ps.println(c);

            // flush the stream
            ps.flush();
        }
    }
    ```

    **输出:**

    ```java
    GeeksforGeeks
    ```

*   **protected void setError() :**Sets the error state of the stream to true.

    ```java
    Syntax :public void println(String x)
    ```

    ```java
    //Java program to demonstrate setError() method
    import java.io.*;

    public class PrintStreamDemo extends PrintStream 
    {
        public PrintStreamDemo(OutputStream out) 
        {
            super(out);
        }
        public static void main(String[] args) 
        {
            byte c[] = {65, 66, 67, 68, 69, 70, 71};

            // create printstream object
            PrintStreamDemo obj = new PrintStreamDemo(System.out);

            // illustrating write() method
            obj.write(c, 1, 3);

            // flush the stream
            obj.flush();

            //illustrating setError() method 
            obj.setError();
        }
    }
    ```

    **输出:**

    ```java
    BCD

    ```

*   **void write(byte[] buf, int off, int len) :**Writes len bytes from the specified byte array starting at offset off to this stream.

    ```java
    Syntax :public void write(byte[] buf,
             int off,
             int len)
    Overrides:
    write in class FilterOutputStream
    Parameters:
    buf - A byte array
    off - Offset from which to start taking bytes
    len - Number of bytes to write
    ```

    ```java
    //Java program to demonstrate write(int b) method
    import java.io.*;

    public class PrintStreamDemo 
    {
        public static void main(String[] args) 
        {
            byte c = 65;

            // create printstream object
            PrintStream obj = new PrintStream(System.out);

            //illustrating write(int b)
            obj.write(c);

            // flush the stream
            obj.flush();

        }
    }
    ```

    **输出:**

    ```java
    BCD
    ```

*   **void write(int b) :**Writes the specified byte to this stream.

    ```java
    Syntax :public void write(int b)
    Overrides:
    write in class FilterOutputStream
    Parameters:
    b - The byte to be written
    ```

    ```java
    //Java program to demonstrate write(int b) method
    import java.io.*;

    public class PrintStreamDemo 
    {
        public static void main(String[] args) 
        {
            byte c = 65;

            // create printstream object
            PrintStream obj = new PrintStream(System.out);

            //illustrating write(int b)
            obj.write(c);

            // flush the stream
            obj.flush();

        }
    }
    ```

    **输出:**

    ```java
    A
    ```

本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766?ref=bookmarks)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。