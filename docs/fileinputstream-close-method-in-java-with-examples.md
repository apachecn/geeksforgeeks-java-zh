# Java 中的 FileInputStream close()方法，带示例

> 原文:[https://www . geesforgeks . org/file inputstream-close-method-in-Java-with-examples/](https://www.geeksforgeeks.org/fileinputstream-close-method-in-java-with-examples/)

FileInputStream 类有助于以字节序列的形式从文件中读取数据。FileInputStream 用于读取原始字节流，如图像数据。要读取字符流，请考虑使用文件阅读器。

### **FileInputStream.close()方法**

对文件进行任何操作后，我们必须关闭该文件。为此，我们有一个封闭的方法。我们将在本文中了解到这一点。 **FileInputStream.close()** 方法关闭该文件输入流，并释放与该流相关联的任何系统资源。

**语法:**

```java
FileInputStream.close()
```

**返回值:**该方法不返回值。

**异常:** *异常*:如果出现任何输入/输出错误。

#### **如何调用** **合()法？**

**步骤 1:** 将文件附加到文件输入流，因为这将使我们能够关闭文件，如下所示:

```java
FileInputStream  fileInputStream =new FileInputStream(“file.txt”);
```

**第二步:**要关闭文件，我们必须使用上面的实例调用 close()方法。

```java
fileInputStream.close(); 
```

**进场:**

1.我们将首先读取一个文件，然后关闭它。

2.关闭文件后，我们将再次尝试读取它。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate the working
// of the FileInputStream close() method

import java.io.File;
import java.io.FileInputStream;

public class abc {

    public static void main(String[] args)
    {

        // Creating file object and specifying path
        File file = new File("file.txt");

        try {
            FileInputStream input
                = new FileInputStream(file);
            int character;
            // read character by character by default
            // read() function return int between
            // 0 and 255.

            while ((character = input.read()) != -1) {
                System.out.print((char)character);
            }

            input.close();
            System.out.println("File is Closed");
            System.out.println(
                "Now we will again try to read");
            while ((character = input.read()) != -1) {
                System.out.print((char)character);
            }
        }
        catch (Exception e) {
            System.out.println(
                "File is closed. Cannot be read");
            e.printStackTrace();
        }
    }
}
```

**输出**

```java
GeeksforGeeks is a computer science portal
File is Closed
Now we will again try to read
File is closed. Cannot be read
java.io.IOException: Stream Closed
       at java.base/java.io.FileInputStream.read0(Native Method)
       at java.base/java.io.FileInputStream.read(Unknown Source)
       at abc.main(abc.java:28)
```

> **注意:**此代码不会在联机 IDE 上运行，因为它需要系统上的一个文件。