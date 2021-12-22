# java 中的 java.nio.file.FileSystem 类

> 原文:[https://www . geesforgeks . org/Java-nio-file-file system-in-Java 类/](https://www.geeksforgeeks.org/java-nio-file-filesystem-class-in-java/)

**java.nio.file.FileSystem** 类提供了一个文件系统的接口。文件系统充当创建不同对象的工厂，如路径、路径匹配器、**用户原则允许用户服务、**和**监视服务**。该对象有助于访问**文件系统中的文件和其他对象。**

****语法:**类声明**

```
public abstract class FileSystem
extends Object
implements Closeable
```

**此类的构造函数如下:**

<figure class="table">

| 构造器 | 描述 |
| --- | --- |
| 文件系统() | 创建文件系统类的新对象 |

</figure>

**该类的方法如下:**

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| 关闭() | 关闭已打开的文件系统。 |
| getFileStores() | 返回一个 iterable 对象，该对象用于遍历基础文件存储。 |
| 获取路径(字符串优先，字符串…更多) | 将给定的字符串转换为路径，或者组合给定的字符串序列以形成路径。 |
| getpathmatcher(字符串 syntaxAndPattern) | 返回一个路径匹配器对象，用于对路径对象执行匹配操作。 |
| getRootDirectories() | 返回一个可迭代对象，用于迭代根目录。 |
| getSeparator() | 返回名称分隔符的字符串表示形式。 |
| getUserPrincipalLookupService() | 返回此文件系统的 UserPrincipalLookupService 对象。这是一个可选操作。 |
| 等轴测() | 用于检查该文件系统是否打开。 |
| isReadOnly（） | 用于检查此文件系统是否允许对其文件存储进行只读访问。 |
| newWatchService() | 返回一个新的 WatchService 对象。 |
| 提供商() | 返回创建此文件系统的提供程序。 |
| supportedFileAttributeViews() | 返回由该文件系统支持的文件属性视图的名称组成的集合。 |

</figure>

****例 1:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java program to Create a new FileSystem object and
// print its file stores and root directories

// Importing required classes from java.nio package
// Importing input output classes
import java.io.*;
import java.nio.file.FileStore;
import java.nio.file.FileSystem;
import java.nio.file.FileSystems;
import java.nio.file.Path;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Try block to check for exceptions
        try {
            // Create a new File system Object
            FileSystem filesystem
                = FileSystems.getDefault();

            // Display messages only
            System.out.println(
                "File System created successfully");

            System.out.println(
                "Underlying file stores of this FileSystem :");

            // Print the Underlying file stores of this
            // FileSystem using for each loop
            for (FileStore store :
                 filesystem.getFileStores()) {
                System.out.println(store.toString());
            }

            // Display message only
            System.out.println(
                "Root directories of this FileSystem :");

            for (Path rootdir :
                 filesystem.getRootDirectories()) {

                // Print the Root directories of this
                // FileSystem using standard toString()
                // method
                System.out.println(rootdir.toString());
            }
        }

        // Catch block to handle exceptions
        catch (Exception e) {

            // Print the exception along with
            // line number where it occurred
            e.printStackTrace();
        }
    }
}
```

****输出:****

```
File System created successfully
Underlying file stores of this FileSystem :
/ (/dev/disk1s1)
/dev (devfs)
/private/var/vm (/dev/disk1s4)
/net (map -hosts)
/home (map auto_home)
Root directories of this FileSystem :
/
```

****例 2:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java program to illustrate Working of FileSystem Class
// Via its Methods

// importing required classes from java.nio package
// Importing input output classes
import java.io.*;
import java.nio.file.FileSystem;
import java.nio.file.FileSystems;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Try block to check for exceptions
        try {

            // Creating an object of FileSystem class in the
            // main() method using getDefault() method
            FileSystem filesystem
                = FileSystems.getDefault();

            // Display message only
            System.out.println(
                "FileSystem created successfully");

            // Checking if file system is open or close
            if (filesystem.isOpen())

                // Print statement
                System.out.println("File system is open");
            else

                // Print statement
                System.out.println("File system is close");

            // Check if file system is read-only
            if (filesystem.isReadOnly())

                // Print statement
                System.out.println(
                    "File system is Read-only");
            else

                // Print statement
                System.out.println(
                    "File system is not Read-only");

            // Now, print the name separator
            // using getSeparator() method
            System.out.println("Separator: "
                               + filesystem.getSeparator());

            // Print hash value of this file system
            // using hashCode() method
            System.out.println("Hashcode: "
                               + filesystem.hashCode());

            // Print provider of this file system
            System.out.println(
                "Provider: "
                + filesystem.provider().toString());
        }

        // Catch block to handle the exceptions
        catch (Exception e) {

            // Print the exception along with line number
            // using printStackTrace() method and
            // display it on the console
            e.printStackTrace();
        }
    }
}
```

****输出:****

```
FileSystem created successfully
File system is open
File system is not Read-only
Separator: /
Hashcode: 929338653
Provider: sun.nio.fs.MacOSXFileSystemProvider@4b1210ee 
```