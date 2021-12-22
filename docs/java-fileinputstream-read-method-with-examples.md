# Java 文件输入流读取()方法示例

> 原文:[https://www . geesforgeks . org/Java-file inputstream-read-method-with-examples/](https://www.geeksforgeeks.org/java-fileinputstream-read-method-with-examples/)

Java 中的 FileInputStream 类对于以字节序列的形式从文件中读取数据非常有用。FileInputStream 用于读取原始字节流，如图像数据。要读取字符流，请考虑使用文件阅读器。

InputStream 类的 **read()方法从输入流中读取一个字节的数据。返回数据的下一个字节，如果到达文件的末尾，则返回-1，如果出现输入/输出错误，则抛出异常。参考程序。**

**语法:**

```
public abstract int read()
```

**返回值:**这个方法返回下一个字节的数据，如果到达流的末尾，返回-1。

**异常:** *异常*:如果出现输入输出错误。

### **如何调用**的**read()方法？**

按照以下步骤使用文件输入流从文件中读取数据，这是文件输入类的最终目标

**步骤 1:** 将文件附加到文件输入流，因为这将使我们能够从文件中读取数据，如下所示:

```
FileInputStream  fileInputStream =new FileInputStream(“file.txt”);
```

**步骤 2:** 现在，要从文件中读取数据，我们应该从文件输入流中读取数据，如下所示:

```
ch=fileInputStream.read();
```

**步骤 3(a):** 当没有更多数据可供进一步读取时，read()方法返回-1；

**步骤 3(b):** 然后，我们应该将监视器附加到输出流。为了显示数据，我们可以使用系统打印

```
System.out.print(ch);
```

### **实施:**

**原始文件内容:(“File . txt”)**

```
GeeksforGeeks is a computer science portal
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the working
// of the FileInputStream read() method

import java.io.File;
import java.io.FileInputStream;

public class abc {

    public static void main(String[] args) {       

            // Creating file object and specifying path
            File file = new File("file.txt");

            try {
                FileInputStream input= new FileInputStream(file);
                int character;
                // read character by character by default
                // read() function return int between 0 and 255.

                while ((character = input.read()) != -1) {
                    System.out.print((char)character);
                }
            }
            catch (Exception e) {
                e.printStackTrace();
            }
    }
}
```

**输出**

```
GeeksforGeeks is a computer science portal
```

### **在不使用-1 in while 循环的情况下读取文件**

我们将在本文中使用可用()方法的概念。available()方法用于返回还有多少字节需要读取。我们将使用 read()方法打印字符，直到剩下 0 个字符可供读取。

**示例:原始文件内容:(“File . txt”)**

```
GeeksforGeeks
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to read a file
// without using -1 in while loop

import java.io.File;
import java.io.FileInputStream;

public class abc {

    public static void main(String[] args) {

            // Creating file object and specifying path
            File file = new File("file.txt");

            try {
                FileInputStream input= new FileInputStream(file);
                int character;

                // read character by character by default
                // read() function return int between 0 and 255.
                while (input.available()!=0) {
                    character = input.read();
                    System.out.print((char)character);   
                }

                input.close();   
            }

            catch (Exception e) {

                e.printStackTrace();
            }
    }
}
```

**输出**

```
GeeksforGeeks
```