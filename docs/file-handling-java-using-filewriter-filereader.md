# 使用文件写入器和文件读取器进行 Java 文件处理

> 原文:[https://www . geesforgeks . org/file-handling-Java-using-file writer-file reader/](https://www.geeksforgeeks.org/file-handling-java-using-filewriter-filereader/)

Java FileWriter 和 FileReader 类用于从文本文件中写入和读取数据(它们是[字符流](https://www.geeksforgeeks.org/character-stream-vs-byte-stream-java/)类)。建议**而不是**使用文件输入流和文件输出流类，如果你必须读写任何文本信息，因为这些是字节流类。

**档案作者**

FileWriter 对于创建向其中写入字符的文件非常有用。

*   此类继承自 OutputStream 类。
*   这个类的构造函数假设默认字符编码和默认字节缓冲区大小是可以接受的。要自己指定这些值，请在文件输出流上构造一个输出流编写器。
*   FileWriter 用于编写字符流。要写入原始字节流，请考虑使用文件输出流。
*   如果输出文件还不存在，FileWriter 会创建输出文件。

**施工人员:**

*   **文件写入器(文件文件)–**给定一个文件对象，构造一个文件写入器对象。
*   **文件写入器(文件文件，布尔追加)–**给定一个文件对象，构造一个文件写入器对象。
*   **FileWriter(file descriptor FD)–**构造一个与文件描述符相关联的 file writer 对象。
*   **文件写入器(字符串文件名)–**构造一个给定文件名的文件写入器对象。
*   **文件写入器(字符串文件名，布尔追加)–**为给定的文件名构造一个文件写入器对象，该对象带有一个指示是否追加写入数据的布尔值。

**方法:**

*   **公共 void write (int c)抛出 IOException–**写入单个字符。
*   **公共 void write (char [] stir)抛出 IOException–**写入字符数组。
*   **公共 void write(字符串字符串)抛出 IOException–**写入字符串。
*   **公共 void write(String str，int off，int len)抛出 IOException–**写入字符串的一部分。这里 off 是开始写入字符的偏移量，len 是要写入的字符数。
*   **公共空间刷新()引发 IOException** 刷新流
*   **public void close()抛出 IOException** 先刷新流，然后关闭编写器。

读和写一个字符一个字符地发生，这增加了输入/输出操作的数量，影响了系统的性能。 **BufferedWriter** 可以和 FileWriter 一起使用，提高执行速度。

以下程序描述了如何使用文件编写器创建文本文件

```java
// Creating a text File using FileWriter
import java.io.FileWriter;
import java.io.IOException;
class CreateFile
{
    public static void main(String[] args) throws IOException
    {
        // Accept a string 
        String str = "File Handling in Java using "+
                " FileWriter and FileReader";

        // attach a file to FileWriter 
        FileWriter fw=new FileWriter("output.txt");

        // read character wise from string and write 
        // into FileWriter 
        for (int i = 0; i < str.length(); i++)
            fw.write(str.charAt(i));

        System.out.println("Writing successful");
        //close the file 
        fw.close();
    }
}
```

档案管理员

文件阅读器对于从“文本”文件中读取字符形式的数据非常有用。

*   这个类继承自输入流阅读器类。
*   这个类的构造函数假定默认的字符编码和默认的字节缓冲区大小是合适的。要自己指定这些值，请在文件输入流上构造一个输入流读取器。
*   文件阅读器是用来读取字符流的。要读取原始字节流，请考虑使用文件输入流。

**施工人员:**

*   **文件阅读器(文件文件)–**给定要读取的文件，创建文件阅读器
*   **文件阅读器(文件描述器 FD)–**给定要读取的文件描述器，创建一个新的文件阅读器
*   **文件阅读器(字符串文件名)–**给定要读取的文件的名称，创建一个新的文件阅读器

**方法:**

*   **public int read()抛出 IOException–**读取单个字符。此方法将一直阻塞，直到某个字符可用、出现输入/输出错误或到达流的末尾。
*   **public int read(char[] cbuff)抛出 IOException–**将字符读入数组。此方法将一直阻塞，直到有一些输入可用、出现输入/输出错误或到达流的末尾。
*   **公共抽象 int read(char[] buff，int off，int len)抛出 IOException–**将字符读入数组的一部分。此方法将一直阻塞，直到有一些输入可用、出现输入/输出错误或到达流的末尾。
    参数:
    cbuf–目标缓冲区
    关闭–开始存储字符的偏移量
    len–要读取的最大字符数
*   **公共 void close()抛出 IOException** 关闭阅读器。
*   **公共长跳过(长 n)抛出 IOexception–**跳过字符。此方法将一直阻塞，直到某些字符可用、出现输入/输出错误或到达流的末尾。
    参数:
    n–要跳过的字符数

以下程序描述了如何使用文件阅读器读取“文本”文件

```java
// Reading data from a file using FileReader
import java.io.FileNotFoundException;
import java.io.FileReader;
import java.io.IOException;
class ReadFile
{
    public static void main(String[] args) throws IOException
    {
        // variable declaration
        int ch;

        // check if File exists or not
        FileReader fr=null;
        try
        {
            fr = new FileReader("text");
        }
        catch (FileNotFoundException fe)
        {
            System.out.println("File not found");
        }

        // read from FileReader till the end of file
        while ((ch=fr.read())!=-1)
            System.out.print((char)ch);

        // close the file
        fr.close();
    }
}
```

本文由[尼尚夏尔马](https://www.facebook.com/ChippingEye2766)供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。