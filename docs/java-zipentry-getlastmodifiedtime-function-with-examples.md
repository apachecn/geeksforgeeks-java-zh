# Java ZipEntry GetLastModifiedTiME()函数示例

> 原文:[https://www . geesforgeks . org/Java-zippentry-getlastmodieddime-function-with-examples/](https://www.geeksforgeeks.org/java-zipentry-getlastmodifiedtime-function-with-examples/)

函数 getlastmodietime()是 java.util.zip 包的一部分。该函数返回特定子条目的上次修改时间。
函数返回 FileTime 对象，表示 ZipEntry 的上次修改时间(文件上次修改时间)，如果没有指定上次修改时间，则返回 null。
如果从 ZIP 文件或 ZIP 文件格式的输入流中读取 ZIP 条目，则这是最后一次修改时间，否则最后一次修改时间从条目的日期和时间字段中读取。
**功能签名:**

```java
public FileTime getLastModifiedTime()
```

**语法:**

```java
zip_entry.getLastModifiedTime();
```

**参数:**该功能不需要参数。
**返回值:**该函数返回文件时间对象，表示子条目的上次修改时间。
**异常:**函数不抛出任何异常。

**下面的程序说明了 getLastModifiedTime()函数的使用**

**示例 1:** 我们将创建一个名为 zip_file 的文件，并使用 getEntry()函数获取 zip 文件条目，然后获取指定 ZipEntry 的 LastModifiedTime。“file.zip”是 f:目录中的一个 zip 文件。我们就拍一张”。zip”文件作为 ZipEntry

```java
// Java program to demonstrate the
// use of getLastModifiedTime() function

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

            // Get the LastModifiedTime
            // using the getLastModifiedTime()
            // function
            FileTime input = entry.getLastModifiedTime();

            // Display the LastModifiedTime
            System.out.println("LastModifiedTime : "
                               + input.toString());
        }
        catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**Output:**

```java
LastModifiedTime : 2019-02-24T18:42:15.858576Z

```

**示例 2:** 我们将创建一个名为 zip_file 的文件，并使用 getEntry()函数获取 zip 文件条目，然后获取指定 ZipEntry 的 LastModifiedTime。“file.zip”是 f:目录中的一个 zip 文件。我们就拍一张”。cpp "文件作为 ZipEntry

```java
// Java program to demonstrate the
// use of getLastModifiedTime() function

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

            // Get the LastModifiedTime
            // using the getLastModifiedTime()
            // function
            FileTime input = entry.getLastModifiedTime();

            // Display the LastModifiedTime
            System.out.println("LastModifiedTime : "
                               + input.toString());
        }
        catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**Output:**

```java
LastModifiedTime : 2018-12-07T13:11:25.38081Z

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/zip/ZipEntry . html # GetLastModifiedTiME–](https://docs.oracle.com/javase/8/docs/api/java/util/zip/ZipEntry.html#getLastModifiedTime--)