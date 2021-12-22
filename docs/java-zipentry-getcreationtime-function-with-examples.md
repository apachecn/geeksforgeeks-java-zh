# Java zipcentry getCreationTime()函数示例

> 原文:[https://www . geeksforgeeks . org/Java-zipper entry-getcreation ontime-function-with-examples/](https://www.geeksforgeeks.org/java-zipentry-getcreationtime-function-with-examples/)

函数是 java.util.zip 包的一部分。如果未指定创建时间，该函数将返回特定子条目的创建时间或空值。
函数返回 FileTime Object，表示 ZipEntry 的创建时间。
**功能签名:**

```java
public FileTime getCreationTime()
```

**语法:**

```java
zip_entry.getCreationTime();
```

**参数:**该功能不需要参数。
**返回值:**该函数返回 FileTime 对象，表示 ZipEntry 的创建时间。
**异常:**函数不抛出任何异常。

**下面的程序说明了 getCreationTime()函数的使用**

**示例 1:** 我们将创建一个名为 zip_file 的文件，并使用 getEntry()函数获取 zip 文件条目，然后获取指定 ZipEntry 的 CreationTime。“file.zip”是 f:目录中的一个 zip 文件。我们就拍一张”。zip”文件作为 ZipEntry

```java
// Java program to demonstrate the
// use of getCreationTime() function

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

            // Get the CreationTime
            // using the getCreationTime()
            // function
            FileTime input = entry.getCreationTime();

            // Display the CreationTime
            System.out.println("CreationTime : " + input.toString());
        }
        catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**Output:**

```java
CreationTime : 2019-02-21T21:09:35.688822Z

```

**示例 2:** 我们将创建一个名为 zip_file 的文件，并使用 getEntry()函数获取 zip 文件条目，然后获取指定 ZipEntry 的 CreationTime。“file.zip”是 f:目录中的一个 zip 文件。我们就拍一张”。cpp "文件作为 ZipEntry

```java
// Java program to demonstrate the
// use of getCreationTime() function

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

            // Get the CreationTime
            // using the getCreationTime()
            // function
            FileTime input = entry.getCreationTime();

            // Display the CreationTime
            System.out.println("CreationTime : " + input.toString());
        }
        catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**Output:**

```java
CreationTime : 2018-12-07T13:11:25.357749Z

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/zip/ZipEntry . html # GetCreationTime–](https://docs.oracle.com/javase/8/docs/api/java/util/zip/ZipEntry.html#getCreationTime--)