# Java ZipEntry getSize()函数示例

> 原文:[https://www . geeksforgeeks . org/Java-zip entry-getsize-function-with-examples/](https://www.geeksforgeeks.org/java-zipentry-getsize-function-with-examples/)

函数是 java.util.zip 包的一部分。该函数返回作为参数传递的特定 ZipEntry 的未压缩大小，如果未知，则返回-1。
**功能签名:**

```java
public long getSize()
```

**语法:**

```java
zip_entry.getSize();
```

**参数:**该功能不需要参数。
**返回值:**该函数返回一个长值，即这个 ZipEntry 的未压缩大小。
**异常:**函数不抛出任何异常。

**以下程序说明了 getSize()功能的使用**

**示例 1:** 我们将创建一个名为 zip_file 的文件，并使用 getEntry()函数获取 zip 文件条目，然后获取指定 ZipEntry 的未压缩大小。“file.zip”是 f:目录中的一个 zip 文件。我们就拍一张”。zip”文件作为 ZipEntry

```java
// Java program to demonstrate the
// use of getSize() function

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

            // Get the uncompressed Size
            // using the getSize()
            // function
            long input = entry.getSize();

            // Display the uncompressed Size
            System.out.println("uncompressed Size : " + input);
        }
        catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**Output:**

```java
uncompressed Size : 2153

```

**示例 2:** 我们将创建一个名为 zip_file 的文件，并使用 getEntry()函数获取 zip 文件条目，然后获取指定 ZipEntry 的未压缩大小。“file.zip”是 f:目录中的一个 zip 文件。我们就拍一张”。cpp "文件作为 ZipEntry

```java
// Java program to demonstrate the
// use of getSize() function

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

            // Get the uncompressed Size
            // using the getSize()
            // function
            long input = entry.getSize();

            // Display the uncompressed Size
            System.out.println("uncompressed Size : " + input);
        }
        catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**Output:**

```java
uncompressed Size : 783

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/zip/ZipEntry . html # GetSize–](https://docs.oracle.com/javase/8/docs/api/java/util/zip/ZipEntry.html#getSize--)