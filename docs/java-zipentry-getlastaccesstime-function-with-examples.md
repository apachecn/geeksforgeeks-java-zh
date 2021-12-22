# Java ZipEntry GetLastAccessTime()函数示例

> 原文:[https://www . geeksforgeeks . org/Java-zippentry-getlastacesstime-function-with-examples/](https://www.geeksforgeeks.org/java-zipentry-getlastaccesstime-function-with-examples/)

函数是 java.util.zip 包的一部分。该函数返回特定子条目的上次访问时间。
函数返回 FileTime 对象，表示 ZipEntry 的上次访问时间(文件上次被访问的时间)，如果没有指定上次访问时间，则返回 null。
**功能签名:**

```
public FileTime getLastAccessTime()
```

**语法:**

```
zip_entry.getLastAccessTime();
```

**参数:**该功能不需要参数。
**返回值:**该函数返回文件时间对象，表示子条目的上次访问时间。
**异常:**函数不抛出任何异常。

**以下程序说明了 getLastAccessTime()功能的使用**

**示例 1:** 我们将创建一个名为 zip_file 的文件，并使用 getEntry()函数获取 zip 文件条目，然后获取指定 ZipEntry 的 LastAccessTime。“file.zip”是 f:目录中的一个 zip 文件。我们就拍一张”。zip”文件作为 ZipEntry

```
// Java program to demonstrate the
// use of getLastAccessTime() function

import java.util.zip.*;
import java.util.Enumeration;
import java.util.*;
import java.io.*;
import java.nio.file.attribute.*;

public class solution {
    public static void main(String args[])
    {
        try {
            // Create a Zip File
            ZipFile zip_file = new ZipFile("f:\\file1.zip");

            // get the Zip Entry using
            // the getEntry() function
            ZipEntry entry = zip_file.getEntry("file.zip");

            // Get the LastAccessTime
            // using the getLastAccessTime()
            // function
            FileTime input = entry.getLastAccessTime();

            // Display the LastAccessTime
            System.out.println("LastAccessTime : "
                               + input.toString());
        }
        catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**Output:**

```
LastAccessTime : 2019-02-24T18:42:15.847545Z

```

**示例 2:** 我们将创建一个名为 zip_file 的文件，并使用 getEntry()函数获取 zip 文件条目，然后获取指定 ZipEntry 的 LastAccessTime。“file.zip”是 f:目录中的一个 zip 文件。我们就拍一张”。cpp "文件作为 ZipEntry

```
// Java program to demonstrate the
// use of getLastAccessTime() function

import java.util.zip.*;
import java.util.Enumeration;
import java.util.*;
import java.io.*;
import java.nio.file.attribute.*;

public class solution {
    public static void main(String args[])
    {
        try {
            // Create a Zip File
            ZipFile zip_file = new ZipFile("f:\\file1.zip");

            // get the Zip Entry using
            // the getEntry() function
            ZipEntry entry = zip_file.getEntry("file1.cpp");

            // Get the LastAccessTime
            // using the getLastAccessTime()
            // function
            FileTime input = entry.getLastAccessTime();

            // Display the LastAccessTime
            System.out.println("LastAccessTime : "
                               + input.toString());
        }
        catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**Output:**

```
LastAccessTime : 2018-12-07T13:11:25.38081Z

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/zip/ZipEntry . html # GetLastAccessTime–](https://docs.oracle.com/javase/8/docs/api/java/util/zip/ZipEntry.html#getLastAccessTime--)