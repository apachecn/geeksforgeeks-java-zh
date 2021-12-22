# Java 中的 FileWriter 类

> 原文:[https://www.geeksforgeeks.org/filewriter-class-in-java/](https://www.geeksforgeeks.org/filewriter-class-in-java/)

**Java FileWriter** 类的 java.io 包用于将**字符形式的数据写入**文件。

*   这个类继承自 [OutputStreamWriter 类](https://www.geeksforgeeks.org/java-io-outputstreamwriter-class-methods/)，后者又继承自 Writer 类。
*   这个类的构造函数假设默认字符编码和默认字节缓冲区大小是可以接受的。要自己指定这些值，请在[文件输出流](https://www.geeksforgeeks.org/fileoutputstream-in-java/)上构建一个输出流编写器。
*   FileWriter 用于编写字符流。要写入原始字节流，请考虑使用文件输出流。
*   如果输出文件尚不存在，则 FileWriter 会创建输出文件。

**文件编写器的层次结构**

![Hierarchy of FileWriter](img/02154bac22fdb3d47200a0c3c5c0029f.png)

FileWriter 扩展了 OutputStreamWriter 和 [Writer](https://www.geeksforgeeks.org/java-io-writer-class-java/) 类。它实现了可关闭、可刷新、可追加、可自动关闭的接口。

**file writer 的构造函数**

**1。文件写入器(文件文件):**给定一个文件对象，构造一个文件写入器对象。如果文件存在但不是常规文件，或者不存在但无法创建，或者由于任何其他原因无法打开，它将抛出 **IOException** 。

> File writer fw = newFile writer(文件文件)；

**2。文件写入器(文件文件，布尔追加):**给定一个文件对象，构造一个文件写入器对象。如果第二个参数为真，那么字节将被写入文件的末尾，而不是开头。如果文件存在但不是常规文件，或者不存在但无法创建，或者由于任何其他原因无法打开，它将抛出 **IOException** 。

> File writer fw = newFile writer(文件文件，布尔追加)；

**3。FileWriter(file descriptor FD):**构造一个与文件描述符相关联的 file writer 对象。

> file writer fw = newfile writer(file descriptor FD)；

**4。FileWriter(File file，Charset charset):** 在给定文件和 Charset 的情况下构造 FileWriter。

> File writer fw = newFile writer(文件文件，字符集字符集)；

**5。FileWriter(File file，Charset charset，boolean append):** 当给定文件和 Charset 以及一个指示是否追加写入数据的 boolean 时，构造 FileWriter。

> File writer fw = newFile writer(文件文件，字符集字符集，布尔追加)；

**6。文件写入器(字符串文件名):**构造一个给定文件名的文件写入器对象。

> 文件编写器 fw = new 文件编写器(字符串文件名)；

**7。文件写入器(字符串文件名，布尔追加):**为给定的文件名构造一个文件写入器对象，该对象带有一个布尔值，指示是否追加写入的数据。

> 文件编写器 fw = new 文件编写器(字符串文件名，布尔追加)；

**8。文件编写器(字符串文件名，字符集):**当给定文件名和字符集时，构造一个文件编写器。

> 文件编写器 fw = new 文件编写器(字符串文件名，字符集字符集)；

**9。文件写入器(字符串文件名、字符集、布尔追加):**当给定文件名和字符集以及指示是否追加数据的布尔变量时，构造文件写入器。

> 文件编写器 fw = new 文件编写器(字符串文件名、字符集字符集、布尔追加)；

**申报**

```
public class FileWriter extends OutputStreamWriter 
```

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to create a text File using FileWriter

import java.io.FileWriter;
import java.io.IOException;
import java.util.*;
class GFG {
    public static void main(String[] args)
        throws IOException
    {
        // initialize a string
        String str = "ABC";
        try {

            // attach a file to FileWriter
            FileWriter fw
                = new FileWriter("D:/data/file.txt");

            // read each character from string and write
            // into FileWriter
            for (int i = 0; i < str.length(); i++)
                fw.write(str.charAt(i));

            System.out.println("Successfully written");

            // close the file
            fw.close();
        }
        catch (Exception e) {
            e.getStackTrace();
        }
    }
}
```

![writing ABC string to a file](img/dd1b37110ccd655a4d398ce9d58f7bee.png)

**覆盖与追加文件:**

在创建 Java FileWriter 时，我们可以决定是将文件追加到现有文件，还是覆盖任何现有文件。这可以通过选择适当的构造函数来决定。覆盖任何现有文件的**构造函数只接受**一个参数，即文件名。****

```
Writer fileWriter = new FileWriter("c:\\data\\output.txt");
```

**追加文件**或覆盖文件的构造函数采用**两个参数，文件名和一个布尔变量**，决定是追加还是覆盖文件

> writer file writer = new file writer(" c:\ data \ \ output . txt "，true)；//追加到文件
> 
> writer file writer = new file writer(" c:\ data \ \ output . txt "，false)；//覆盖文件

### 基本方法

**1。Write()**

1.  **write(int a):** 此方法写入 int a 指定的单个字符。
2.  **write(String str，int pos，** **int length):** 此方法从位置 **pos** 一直到 **length** 字符数写入字符串的一部分。
3.  **写入(char ch[]，int pos，int length):** 此方法从位置 **pos** 一直到 **length** 字符数写入数组 ch[]中的字符位置。
4.  **write(char ch[]):** 此方法写入由 ch[]指定的字符数组。
5.  **write(String st):** 此方法将“st”指定的字符串值写入文件。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to write text to file

import java.io.FileWriter;

public class GFG {

    public static void main(String args[])
    {

        String data = "Welcome to gfg";

        try {
            // Creates a FileWriter
            FileWriter output
                = new FileWriter("output.txt");

            // Writes the string to the file
            output.write(data);

            // Closes the writer
            output.close();
        }

        catch (Exception e) {
            e.getStackTrace();
        }
    }
}
```

**2. getEncoding（）**

此方法用于获取用于写入数据的编码类型。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// java program to show the usage
// of getEncoding() function

import java.io.FileWriter;
import java.nio.charset.Charset;

class Main {
    public static void main(String[] args)
    {

        String file = "output.txt";

        try {
            // Creates a FileReader with default encoding
            FileWriter o1 = new FileWriter(file);

            // Creates a FileReader specifying the encoding
            FileWriter o2 = new FileWriter(
                file, Charset.forName("UTF11"));

            // Returns the character encoding of the reader
            System.out.println("Character encoding of o1: "
                               + o1.getEncoding());
            System.out.println("Character encoding of o2: "
                               + o2.getEncoding());

            // Closes the reader
            o1.close();
            o2.close();
        }

        catch (Exception e) {
            e.getStackTrace();
        }
    }
}
```

**输出:**

```
The character encoding of output1: Cp1253
The character encoding of output2: UTF11
```

在上面的例子中，我们创建了两个名为 output1 和 output2 的文件编写器。

1.  **output1:** 未指定字符编码。因此，getEncoding()方法返回默认的字符编码。
2.  **输出 2:** 指定字符编码，**输出 11** 。因此，getEncoding()方法返回指定的字符编码。

**3。close()方法:**

在完成向文件写入器写入字符后，我们应该关闭它。这是通过调用 close()方法来完成的。

```
 try {
     // Creates a FileReader with default encoding
     FileWriter o1 = new FileWriter(file);

     // Creates a FileReader specifying the encoding
     FileWriter o2 = new FileWriter(file, Charset.forName("UTF11"));

     // Returns the character encoding of the reader
     System.out.println("Character encoding of o1: " + o1.getEncoding());
     System.out.println("Character encoding of o2: " + o2.getEncoding());

     // Closes the FileWriter
     o1.close();
     o2.close();
   }
```

**file writer vs file output stream**

*   文件写入器写入字符流，而文件输出流用于写入原始字节流。
*   文件写入器处理 16 位字符，而另一方面，文件输出流处理 8 位字节。
*   FileWriter 处理 Unicode 字符串，而 FileOutputStream 向文件写入字节，它不接受字符或字符串，因此为了接受字符串，它需要用 OutputStreamWriter 包装。

#### 文件编写器的方法

<figure class="table">

| 

方法

 | 描述 |
| --- | --- |
| 无效写入(字符串文本) | 它用于将字符串写入文件写入器。 |
| 无效写入(字符 c) | 它用于将字符写入文件写入器。 |
| 无效写入(字符[] c) | 它用于将字符数组写入文件写入器。 |
| 空隙冲洗() | 它用于刷新文件写入器的数据。 |
| 无效关闭() | 它用于关闭文件写入器。 |

</figure>

#### 输出流编写器的方法

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| 齐平() | 冲洗溪流。 |
| getEncoding() | 返回此流使用的字符编码的名称。 |
| 写入(char[] cbuf，int off，int len) | 写入字符数组的一部分。 |
| 写(int c) | 写一个字符。 |
| 写入(字符串，整数关闭，整数长度) | 写入字符串的一部分。 |

</figure>

#### 作家的方法

<figure class="table">

| 

方法

 | 描述 |
| --- | --- |
| [追加(char c)](https://www.geeksforgeeks.org/writer-appendchar-method-in-java-with-examples/) | 将指定的字符追加到此编写器中。 |
| 附录(CharSequence csq) | 将指定的字符序列追加到此编写器。 |
| append (CharSequence csq、int start、int end) | 向此编写器追加指定字符序列的子序列。 |
| [关闭()](https://www.geeksforgeeks.org/writer-close-method-in-java-with-examples/) | 关闭流，首先刷新它。 |
| nullWriter() | 返回一个丢弃所有字符的新 Writer。 |
| [书写(char[] cbuf)](https://www.geeksforgeeks.org/writer-writechar-method-in-java-with-examples/) | 写入字符数组。 |
| [写(字符串)](https://www.geeksforgeeks.org/writer-writestring-method-in-java-with-examples/) | 写一个字符串。 |

</figure>