# Java ZipEntry set compressed size()函数示例

> 原文:[https://www . geeksforgeeks . org/Java-zip entry-set compressed size-function-with-examples/](https://www.geeksforgeeks.org/java-zipentry-setcompressedsize-function-with-examples/)

setCompressedSize()函数是 java.util.zip 包的一部分。该函数将 Zip 条目的压缩大小设置为指定的长值。
**功能签名:**

```
public void setCompressedSize(long val)
```

**语法:**

```
zip_entry.setCompressedSize(val);
```

**参数:**函数取一个长值作为参数。
**返回值:**函数不返回值。
**异常:**函数不抛出任何异常。

**以下程序说明了 setCompressedSize()功能的使用**

**示例 1:** 我们将创建一个名为 zip_file 的文件，并使用 getEntry()函数获取 zip 文件条目，然后设置指定 zip 条目的压缩大小。“file.zip”是 f:目录中的一个 zip 文件。我们就拍一张”。zip”文件作为 ZipEntry

```
// Java program to demonstrate the
// use of setCompressedSize() function

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

            // set the CompressedSize
            // using the getCompressedSize()
            // function
            entry.setCompressedSize(123);

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
CompressedSize : 123

```

**示例 2:** 我们将创建一个名为 zip_file 的文件，并使用 getEntry()函数获取 zip 文件条目，然后设置指定 ZipEntry 的 CompressedSize。“file.zip”是 f:目录中的一个 zip 文件。我们就拍一张”。cpp "文件作为 ZipEntry

```
// Java program to demonstrate the
// use of setCompressedSize() function

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

            // set the CompressedSize
            // using the getCompressedSize()
            // function
            entry.setCompressedSize(123);

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
CompressedSize : 123

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/zip/ZipEntry . html # setcompressed size-long-](https://docs.oracle.com/javase/8/docs/api/java/util/zip/ZipEntry.html#setCompressedSize-long-)