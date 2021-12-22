# 获取给定文件的字节、千字节和兆字节大小的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-get-size-in-bytes-kb-MB/](https://www.geeksforgeeks.org/java-program-to-get-the-size-of-given-file-in-bytes-kilobytes-and-megabytes/)

java 中内置的 File.length()方法可以用来获取 java 中的文件大小。length()函数是 Java 中 File 类的一部分。该函数返回指定路径的文件长度。如果文件不存在或发生了某种错误，则返回 0。

**参数:**此方法不接受任何参数。

**语法:**

```java
long len = file.length()
```

同样，exists()函数也是 Java 中 File 类的一部分。该函数确定由抽象文件名表示的文件或目录是否存在。如果给定路径的文件存在，函数返回真，否则返回假

**语法:**

```java
file.exists()
```

**参数:**该方法也不接受任何参数。

**返回:**真或假

此示例显示如何使用 file 类的 file.exists()和 file.length()方法获取文件的字节大小。

## 爪哇

```java
// Simple Java Program find  the size of the file
import java.io.File;
public class GFG {
    public static void main(String[] args)
    {
        // create file object enter the path of
        // the file for which size is to be found
        File file = new File("/home/user/GFG.txt");
        if (file.exists()) {
            double bytes = file.length();
            double kilobytes = (bytes / 1024);

            // converting file size to bytes to kb
            double megabytes = (kilobytes / 1024);

            // converting file size tolb to mb
            double gigabytes = (megabytes / 1024);

            System.out.println("bytes : " + bytes);
            System.out.println("kilobytes : " + kilobytes);
            System.out.println("megabytes : " + megabytes);
        }
        else {
            System.out.println("File does not exists!");
        }
    }
}
```

```java
bytes : 17,07,91,615
kilobytes : 1,66,788.686
megabytes : 162.8795766
```

**注意:**如果您想要以千兆字节为单位的文件大小，那么您必须将 mb 值除以 1024，以此类推。

但是现在我们可以在Java 7 之后直接使用 **File.size(路径)**。在这种情况下我们不必创建文件对象我们可以直接找到文件的大小。