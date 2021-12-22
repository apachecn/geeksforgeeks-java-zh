# Java 中的 Java.io.LineNumberReader 类

> 原文:[https://www . geesforgeks . org/Java-io-line number reader-class-Java/](https://www.geeksforgeeks.org/java-io-linenumberreader-class-java/)

跟踪行号的缓冲字符输入流。这个类定义了 setLineNumber(int)和 getLineNumber()方法，分别用于设置和获取当前行号。

*   By default, the line number starts at 0\. When reading data, the number is incremented at each line terminator and can be changed by calling setLineNumber(int).
*   Note, however, that setLineNumber(int) does not actually change the current position in the stream; It only changes the value that getLineNumber () will return.
*   A line is considered to be ended by any one of line feed ('\n'), carriage return ('\r') or carriage return immediately following the line feed.

**构造函数:**

*   **Line number reader (reader in):** Create a new line number reader using the default input buffer size.
*   **Reader in (int SZ):** Create a new line reader to read characters into a buffer of a given size.

**方法:**

*   **线号()**线粗.

    ```java
    Syntax :public int getLineNumber()
    Returns: The current line number
    ```

*   **Invalid mark (int readahead limit):** Mark the current position in the stream. Subsequent calls to reset () will attempt to relocate the stream to this point and will reset the line number appropriately.

    ```java
    Syntax :public void mark(int readAheadLimit)
              throws IOException
    Parameters:
    readAheadLimit - Limit on the number of characters that may be read 
    while still preserving the mark. After reading this many characters, 
    attempting to reset the stream may fail.
    Throws:
    IOException
    ```

*   **int read ():** Read a single character. The line terminator is compressed into a single line feed ('\n'). Whenever the line terminator is read, the current line number is incremented.

    ```java
    Syntax :public int read()
             throws IOException
    Returns:
    The character read, or -1 if the end of the stream has been reached
    Throws:
    IOException
    ```

*   **int read (char [] cbuf, int off, int len):** Read characters into a part of the array. Whenever the line terminator is read, the current line number is incremented.

    ```java
    Syntax :public int read(char[] cbuf,
           int off,
           int len)
             throws IOException
    Parameters:
    cbuf - Destination buffer
    off - Offset at which to start storing characters
    len - Maximum number of characters to read
    Returns:
    The number of bytes read, or -1 if the end of the stream has already been reached
    Throws:
    IOException
    ```

*   **String readline ():** Read a line of text. Whenever the line terminator is read, the current line number is incremented.

    ```java
    Syntax :public String readLine()
                    throws IOException
    Returns: A String containing the contents of the line, not including any line 
    termination characters, or null if the end of the stream has been reached
    Throws:
    IOException
    ```

*   **Void reset ():** Reset the stream to the nearest mark.

    ```java
    Syntax :public void reset()
               throws IOException
    Throws:
    IOException
    ```

*   **无效设置行号(内部行号):**设置当前行号

    ```java
    Syntax :public void setLineNumber(int lineNumber)
    Parameters:
    lineNumber - An int specifying the line number
    ```

*   **Long skip (length n):** Skip characters.

    ```java
    Syntax :public long skip(long n)
              throws IOException
    Parameters:
    n - The number of characters to skip
    Returns:
    The number of characters actually skipped
    Throws:
    IOException
    IllegalArgumentException
    ```

    T42

**程序:**

```java
//Java program demonstrating LineNumberReader methods
import java.io.FileReader;
import java.io.IOException;
import java.io.LineNumberReader;
class LineNumberReaderDemo
{
    public static void main(String[] args) throws IOException 
    {
        FileReader fr = new FileReader("file.txt");
        LineNumberReader lnr = new LineNumberReader(fr);
        char c[] = new char[20];

        //illustrating setLineNumber()
        lnr.setLineNumber(0);

        //illustrating set
        System.out.println(lnr.getLineNumber());

        //illustrating markSupported() method
        if(lnr.markSupported())
        {
            System.out.println("mark() method is supported");
            //illustrating mark method
            lnr.mark(100);
        }

        /*File Contents
        * This is first line
        this is second line
        This is third line
        */

        //skipping 19 characters
        lnr.skip(19);

        //illustrating ready() method
        if(lnr.ready())
        {
            //illustrating readLine() method
            System.out.println(lnr.readLine());

            //illustrating read(char c[],int off,int len)
            lnr.read(c);
            for (int i = 0; i <20 ; i++)
            {
                System.out.print(c[i]);
            }

            //illustrating reset() method
            lnr.reset();

            for (int i = 0; i <18 ; i++)
            {
                //illustrating read() method
                System.out.print((char)lnr.read());
            }
            int ch;

            //illustrating read() method
            System.out.println(lnr.readLine());
            while((ch = lnr.read())==1)
                System.out.print((char)ch);
        }

        //close the stream
        lnr.close();
    }
}
```

**输出:**

```java
0
mark() method is supported
this is second line
This is third line
This is first line
```

本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。