# Java ZipEntry getCrc()函数示例

> 原文:[https://www . geeksforgeeks . org/Java-zipper entry-getcrc-function-with-examples/](https://www.geeksforgeeks.org/java-zipentry-getcrc-function-with-examples/)

函数是 java.util.zip 包的一部分。该函数返回特定 ZipEntry 的 CRC–32 校验和值。
CRC 是用于检测原始数据中的错误的错误检测码。
**功能签名:**

```
public long getCrc()
```

**语法:**

```
zip_entry.getCrc();
```

**参数:**该功能不需要参数。
**返回值:**该函数返回一个长值，即这个 ZipEntry 的 Crc。
**异常:**函数不抛出任何异常。0

**下面的程序说明了 getCrc()函数的使用**

**示例 1:** 我们将创建一个名为 zip_file 的文件，并使用 getEntry()函数获取 zip 文件条目，然后获取指定 ZipEntry 的 CRC-32。“file.zip”是 f:目录中的一个 zip 文件。我们就拍一张”。zip”文件作为 ZipEntry

```
// Java program to demonstrate the
// use of getCrc() function

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

            // Get the Crc
            // using the getCrc()
            // function
            long input = entry.getCrc();

            // Display the Crc
            System.out.println("Crc : " + input);
        }
        catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**Output:**

```
Crc : 1798120178

```

**示例 2:** 我们将创建一个名为 zip_file 的文件，并使用 getEntry()函数获取 zip 文件条目，然后获取指定 ZipEntry 的 CRC-32。“file.zip”是 f:目录中的一个 zip 文件。我们就拍一张”。cpp "文件作为 ZipEntry

```
// Java program to demonstrate the
// use of getCrc() function

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

            // Get the Crc
            // using the getCrc()
            // function
            long input = entry.getCrc();

            // Display the Crc
            System.out.println("Crc : " + input);
        }
        catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**Output:**

```
Crc : 3528251335

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/zip/ZipEntry . html # GetCRc–](https://docs.oracle.com/javase/8/docs/api/java/util/zip/ZipEntry.html#getCrc--)