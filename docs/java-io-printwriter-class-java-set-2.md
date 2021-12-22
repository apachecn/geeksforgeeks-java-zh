# Java 中的 Java.io.PrintWriter 类|第 2 集

> 原文:[https://www . geesforgeks . org/Java-io-print writer-class-Java-set-2/](https://www.geeksforgeeks.org/java-io-printwriter-class-java-set-2/)

[Java 中的 Java.io.PrintWriter 类|集 1](https://www.geeksforgeeks.org/java-io-printwriter-class-java-set-1/)
**更多方法:**

*   **PrintWriter printf(Locale l，String format，Object… args) :** 一种使用指定的格式字符串和参数将格式化字符串写入此编写器的便捷方法。

    ```java
    Syntax :public PrintWriter printf(Locale l,
            String format,
            Object... args)
    Parameters: l - The locale to apply during formatting. If l is null then no localization is applied.
    format - A format string as described in Format string syntax
    args - Arguments referenced by the format specifiers in the format string.
    Returns: This writer
    Throws:
    IllegalFormatException
    NullPointerException
    ```

    ```java
    import java.io.*;
    import java.util.Locale;
    //Java program to demonstrate printf method
    public class PrintWriterDemo {
        public static void main(String[] args) {
            String s = "for";

            // create PrintWriter object
            PrintWriter pr= new PrintWriter(System.out);

            // printf this string
            pr.printf(Locale.CANADA, "Geeks%sGeeks", s);

            // flush the stream
            pr.flush();

        }
    }
    ```

    ```java
    Output:
    GeeksforGeeks
    ```

*   **PrintWriter printf(字符串格式，Object… args) :** 使用指定的格式字符串和参数将格式化字符串写入此编写器的一种方便方法。

    ```java
    Syntax :public PrintWriter printf(String format,
            Object... args)
    Parameters:
    format - A format string as described in Format string syntax
    args - Arguments referenced by the format specifiers in the format string.
    Returns: This writer
    Throws:
    IllegalFormatException
    NullPointerException
    ```

    ```java
    import java.io.*;
    //Java program to demonstrate printf(String format, Object... args) method
    public class PrintWriterDemo {
        public static void main(String[] args) {
            String s = "for";

            // create PrintWriter object
            PrintWriter pr= new PrintWriter(System.out);

            // printf this string
            pr.printf("Geeks%sGeeks", s);

            // flush the stream
            pr.flush();

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
      import java.io.*;
    //Java program to demonstrate println() method
    public class PrintWriterDemo {
        public static void main(String[] args) {
            String s = "GeeksforGeeks";

            // create PrintWriter object
            PrintWriter pr= new PrintWriter(System.out);

            // printf this string
            pr.printf("%s", s);

            // flush the stream
            pr.flush();

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
    import java.io.*;
    //Java program to demonstrate println(boolean) method
    public class PrintWriterDemo {
        public static void main(String[] args) {

            // create PrintWriter object
            PrintWriter pr= new PrintWriter(System.out);

            // print a boolean and change line
            pr.println(true);
            pr.print("New Line");

            // flush the stream
            pr.flush();

        }
    }
    ```

    ```java
    Output:
    true
    New Line
    ```

*   **void println(char x):** 打印一个字符，然后结束该行。

    ```java
    Syntax :public void println(char x)
    ```

    ```java
    import java.io.*;
    //Java program to demonstrate println(char x) method
    public class PrintWriterDemo {

        public static void main(String[] args) {
            char c = 'a';

            // create PrintWriter object
            PrintWriter pr= new PrintWriter(System.out);

            // print a char and change line
            pr.println(c);
            pr.println('b');

            // flush the stream
            pr.flush();

        }
    }
    ```

    ```java
    Output:
    a
    b
    ```

*   **void println(char[] x):** 打印一个字符数组，然后结束该行。

    ```java
    Syntax :public void println(char[] x)
    ```

    ```java
    import java.io.*;
    //Java program to demonstrate println(char[] x) method
    public class PrintWriterDemo {
        public static void main(String[] args) {
            char[] c = {'a', 'b', 'c'};

            // create PrintWriter object
            PrintWriter pr= new PrintWriter(System.out);

            // print an array and change line
            pr.println(c);

            // flush the stream
            pr.flush();

        }
    }
    ```

    ```java
    Output:
    abc

    ```

*   **void println(double x):** Prints a double and then terminate the line.

    ```java
    Syntax :public void println(double x)
    ```

    ```java
    import java.io.*;
    //Java program to demonstrate println(double x) method
    public class PrintWriterDemo {
        public static void main(String[] args) {
            double c = 176.348;

            // create PrintWriter object
            PrintWriter pr= new PrintWriter(System.out);

            // print a double and change line
            pr.println(c);

            // flush the stream
            pr.flush();

        }
    }
    ```

    **输出:**

    ```java
    176.348
    ```

*   **void println(float x):** Prints a float and then terminate the line.

    ```java
    Syntax :public void println(float x)
    ```

    ```java
    //Java program to demonstrate println(float x) method
     import java.io.*;
    public class PrintWriterDemo {

        public static void main(String[] args) {
            float c = 5.76348f;

            // create PrintWriter object
            PrintWriter pr= new PrintWriter(System.out);

            // print a float and change line
            pr.println(c);

            // flush the stream
            pr.flush();

        }
    }
    ```

    **输出:**

    ```java
    5.76348
    ```

*   **void println(int x):** Prints an integer and then terminate the line.

    ```java
    Syntax :public void println(boolean x)
    ```

    ```java
    import java.io.*;
    //Java program to demonstrate println(int x) method
    public class PrintWriterDemo {

        public static void main(String[] args) {
            int c = 15;

            // create PrintWriter object
            PrintWriter pr= new PrintWriter(System.out);

            // print an integer and change line
            pr.println(c);

            // flush the stream
            pr.flush();

        }
    }
    ```

    **输出:**

    ```java
    15

    ```

*   **void println(long x):** Prints a long integer and then terminate the line.

    ```java
    Syntax :public void println(long x)
    ```

    ```java
            import java.io.*;
    //Java program to demonstrate println(long x) method
    public class PrintWriterDemo {

        public static void main(String[] args) {
            long c = 1252344125l;
            try {
                // create PrintWriter object
                PrintWriter pr= new PrintWriter(System.out);

                // print a long and change line
                pr.println(c);

                // flush the stream
                pr.flush();

            } catch (Exception ex) {
                ex.printStackTrace();
            }
        }
    }
    ```

    **输出:**

    ```java
    1252344125
    ```

*   **void println(Object x) :**Prints an Object and then terminate the line.

    ```java
    Syntax :public void println(Object x)
    ```

    ```java
            import java.io.*;
    //Java program to demonstrate println(Object x) method
    public class PrintWriterDemo {

        public static void main(String[] args) {
            Object c = 10;

            // create PrintWriter object
            PrintWriter pr= new PrintWriter(System.out);

            // print an object and change line
            pr.println(c);

            // flush the stream
            pr.flush();

        }
    }
    ```

    **输出:**

    ```java
    10
    ```

*   **void println(String x) : **Prints a String and then terminate the line.

    ```java
    Syntax :public void println(boolean x)
    ```

    ```java
    import java.io.*;
    //Java program to demonstrate println(String x) method
    public class PrintWriterDemo {

        public static void main(String[] args) {
            String c = "GeeksforGeeks";

            // create PrintWriter object
            PrintWriter pr= new PrintWriter(System.out);

            // print a string and change line
            pr.println(c);

            // flush the stream
            pr.flush();

        }
    }
    ```

    **输出:**

    ```java
    GeeksforGeeks
    ```

*   **protected void setError() : **Sets the error state of the stream to true.

    ```java
    Syntax :public void println(String x)
    ```

    ```java
    import java.io.*;
    //Java program to demonstrate setError() method
    public class PrintWriterDemo extends PrintWriter {

        public PrintWriterDemo(OutputStream out) {
            super(out);
        }

        public static void main(String[] args) {
            char c[] = {70, 71, 72, 73, 74, 75, 76};

            // create PrintWriter object
            PrintWriterDemo pr= new PrintWriterDemo(System.out);

            // write char 1-3
            pr.write(c, 1, 3);

            // flush the stream
            pr.flush();

            // set an internal error
            pr.setError();
        }
    }
    ```

    **输出:**

    ```java
    GHI

    ```

*   **void write(char [] buf, int off, int len) : **Writes len char from the specified char array starting at offset off to this stream.

    ```java
    Syntax :public void write(char [] buf,
            int off,
            int len)
    Overrides:
    write in class FilterOutputStream
    Parameters:
    buf - A char array
    off - Offset from which to start taking char 
    len - Number of char to write
    ```

    ```java
    import java.io.*;
    //Java program to demonstrate write() method
    public class PrintWriterDemo {

        public static void main(String[] args) {
            char c[] = {70, 71, 72, 73, 74, 75, 76};
            // create PrintWriter object
            PrintWriter pr= new PrintWriter(System.out);

            // write char 1-3
            pr.write(c, 1, 3);

            // flush the stream
            pr.flush();

        }
    }
    ```

    **输出:**

    ```java
    GHI
    ```

*   **void write(int b) : **Writes the specified char to this stream.

    ```java
    Syntax :public void write(int b)
    Overrides:
    write in class Writer
    Parameters:
     b - The char to be written
    ```

    ```java
    import java.io.*;
    //Java program to demonstrate write(int b) method
    public class PrintWriterDemo {

        public static void main(String[] args) {
            int c = 70;

            // create PrintWriter object
            PrintWriter pr= new PrintWriter(System.out);

            // write char c which is character F in ASCII
            pr.write(c);

            // flush the stream
            pr.flush();

        }
    }
    ```

    **输出:**

    ```java
    F
    ```

*   **空写(字符串):**写字符串。

    ```java
    Syntax :public void write(String s)
    Parameters:
    s - String to be written

    ```

    ```java
    import java.io.*;
    public class PrintWriterDemo {

       public static void main(String[] args) {
          String s = "Hello";
          try {

             // create a new writer
             PrintWriter pw = new PrintWriter(System.out);

             // write strings
             pw.write(s);
             pw.write(" World");

             // flush the writer
             pw.flush();

          } catch (Exception ex) {
             ex.printStackTrace();
          }
       }
    }
    ```

    ```java
    Hello World
    ```

*   **无效写入(字符串 s，int off，int len) :** 写入字符串的一部分。

    ```java
    Syntax :public void write(String s,
             int off,
             int len)
    Parameters:
    s - A String
    off - Offset from which to start writing characters
    len - Number of characters to write

    ```

    ```java
    import java.io.*;

    public class PrintWriterDemo {

       public static void main(String[] args) {
          String s = "Hello World";
          try {

             // create a new writer
             PrintWriter pw = new PrintWriter(System.out);

             // write substrings
             pw.write(s, 0, 5);
             pw.write(s, 6, 5);

             // flush the writer
             pw.flush();

          } catch (Exception ex) {
             ex.printStackTrace();
          }
       }
    }
    ```

    ```java
    HelloWorld
    ```

本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766?ref=bookmarks)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论