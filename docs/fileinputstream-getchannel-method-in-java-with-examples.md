# Java 中的 FileInputStream getChannel()方法，带示例

> 原文:[https://www . geesforgeks . org/file inputstream-getchannel-method-in-Java-with-examples/](https://www.geeksforgeeks.org/fileinputstream-getchannel-method-in-java-with-examples/)

**getChannel()** 方法是 [Java.io.FileInputStream](https://www.geeksforgeeks.org/java-io-fileinputstream-class-java/) 类的一部分。此方法将返回与文件输入流关联的唯一文件通道对象。

*   从 Java.io.FileInputStream 实例的 getChannel()方法获得的通道将被“打开以供读取”
*   getChannel()将返回与“this”file inputstream 实例关联的文件通道对象。
*   每当我们从这个流中读取字节时，通道位置就会改变。
*   每当频道的位置改变时，流的文件位置也会改变。
*   从文件中读取的字节数将决定返回通道的初始位置。

**语法:**

```
public FileChannel getChannel()
```

**参数:** getChannel()方法没有参数。

**返回类型:** getChannel()方法将返回一个唯一的 FileChannel 对象。

### **如何调用 getChannel()方法？**

**步骤 1:** 首先，我们必须创建一个 Java.io.FileInputStream 类的实例

```
FileInputStream  fileInputStream =new FileInputStream("tmp.txt");
```

**第 2 步:**要获取与这个 fileInputStream 关联的唯一 FileChannel 对象，我们将调用 getChannel()方法

```
FileChannel fileChannel = fileInputStream.getChannel();
```

下面的程序将说明 getChannel()方法的使用。

**示例:**程序获取文件通道对象，然后打印通道文件的大小

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to demonstrate the working
// of the FileChannel object and then to
// print the size of the channel's file

import java.io.*;
// import FileChannel
import java.nio.channels.FileChannel;

class GFG {
    public static void main(String[] args)
    {

        try {
            // create instance of FileInputStream class
            // user should change name of the file
            FileInputStream fileInputStream
                = new FileInputStream(
                    "C://geeksforgeeks//tmp.txt");

            // if the specified file does not exist
            if (fileInputStream == null) {
                System.out.println(
                    "Cannot find the specified file");
                return;
            }

            // to get the unique object of FileChannel for
            // this specified fileInputStream
            FileChannel fileChannel
                = fileInputStream.getChannel();

            // print the current size of the channel's file
            System.out.println(
                "Current Size of the file is : "
                + fileChannel.size());
        }
        catch (Exception exception) {
            System.out.println(exception.getMessage());
        }
    }
}
```

**输出:**

```
Current size of the file is 48
```

![](img/3a754515c068b0e1f353ad0a4529d08c.png)

tmp.txt

> **注意:**程序可能无法在在线 IDE 中运行。请使用脱机集成开发环境并更改文件名