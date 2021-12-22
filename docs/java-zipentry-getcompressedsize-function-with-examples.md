# Java ZipEntry getcompressed size()函数示例

> 原文:[https://www . geesforgeks . org/Java-zip entry-get compressed size-function-with-examples/](https://www.geeksforgeeks.org/java-zipentry-getcompressedsize-function-with-examples/)

getCompressedSize()函数是 java.util.zip 包的一部分。该函数返回特定 ZipEntry 的压缩大小，如果不知道，则返回-1。
**功能签名:**

```
public long getCompressedSize()
```

**语法:**

```
zip_entry.getCompressedSize();
```

**参数:**该功能不需要参数。
**返回值:**该函数返回一个长值，即这个子条目的压缩大小。
**异常:**函数不抛出任何异常。

**下面的程序说明了 getCompressedSize()函数的使用**

**示例 1:** 我们将创建一个名为 zip_file 的文件，并使用 getEntry()函数获取 zip 文件条目，然后获取指定 ZipEntry 的压缩大小。“file.zip”是 f:目录中的一个 zip 文件。我们就拍一张”。zip”文件作为 ZipEntry

```
// Java program to demonstrate the
// use of getCompressedSize() function

import java.util.zip.*;
import java.util.Enumeration;
import java.util.*;
import java.io.*;

public class solution {
    public static void main(String args[])
    {
        try {
            // Create a Zip File
            ZipFile zip_file = new ZipFile("f:\\file1.zip");

            // get the Zip Entry using
            // the getEntry() function
            ZipEntry entry = zip_file.getEntry("file.zip");

            // Get the CompressedSize
            // using the getCompressedSize()
            // function
            long input = entry.getCompressedSize();

            // Display the CompressedSize
            System.out.println("CompressedSize : " + input);
        }
        catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**Output:**

```
CompressedSize : 2022

```

**示例 2:** 我们将创建一个名为 zip_file 的文件，并使用 getEntry()函数获取 zip 文件条目，然后获取指定 ZipEntry 的 CompressedSize。“file.zip”是 f:目录中的一个 zip 文件。我们就拍一张”。cpp "文件作为 ZipEntry

```
// Java program to demonstrate the
// use of getCompressedSize() function

import java.util.zip.*;
import java.util.Enumeration;
import java.util.*;
import java.io.*;

public class solution {
    public static void main(String args[])
    {
        try {
            // Create a Zip File
            ZipFile zip_file = new ZipFile("f:\\file1.zip");

            // get the Zip Entry using
            // the getEntry() function
            ZipEntry entry = zip_file.getEntry("file1.cpp");

            // Get the CompressedSize
            // using the getCompressedSize()
            // function
            long input = entry.getCompressedSize();

            // Display the CompressedSize
            System.out.println("CompressedSize : " + input);
        }
        catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**Output:**

```
CompressedSize : 291

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/zip/ZipEntry . html # getcompressed size–](https://docs.oracle.com/javase/8/docs/api/java/util/zip/ZipEntry.html#getCompressedSize--)