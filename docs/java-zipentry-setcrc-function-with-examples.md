# Java ZipEntry setCrc()函数示例

> 原文:[https://www . geeksforgeeks . org/Java-zipper entry-setcrc-function-with-examples/](https://www.geeksforgeeks.org/java-zipentry-setcrc-function-with-examples/)

函数 **setCrc()** 是 java.util.zip 包的一部分。该函数用于设置指定邮政编码条目的循环冗余校验值。循环冗余校验是一种错误检测码，用于检测原始数据中的错误。
**功能签名:**

```
public void setCrc(long val)
```

**语法:**

```
zip_entry.setCrc(val);
```

**参数:**函数取长值，代表 CRC 值
**返回值:**函数不返回值。
**异常:**如果指定的 CRC-32 值小于 0 或大于 0xFFFFFFFF，该函数将抛出 **IllegalArgumentException**

**以下程序说明了 setCrc()功能的使用**

**示例 1:** 我们将创建一个名为 zip_file 的文件，并使用 setEntry()函数获取 zip 文件条目，然后设置指定 ZipEntry 的 CRC-32。“file.zip”是 f:目录中的一个 zip 文件。我们将采取一个”。zip”文件作为 ZipEntry

```
// Java program to demonstrate the
// use of setCrc() function

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

            // set the Zip Entry using
            // the setEntry() function
            ZipEntry entry = zip_file.getEntry("file.zip");

            // set the Crc
            // using the setCrc()
            // function
            entry.setCrc(190);

            // get the Crc
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
Crc : 190

```

**示例 2:** 我们将创建一个名为 zip_file 的文件，并使用 getEntry()函数获取 zip 文件条目，然后设置指定 ZipEntry 的 CRC-32。“file.zip”是 f:目录中的一个 zip 文件。我们将 CRC 的值设置为-1。我们将采取一个”。cpp "文件作为 ZipEntry

```
// Java program to demonstrate the
// use of setCrc() function

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

            // set the Zip Entry using
            // the setEntry() function
            ZipEntry entry = zip_file.getEntry("file1.cpp");

            // set the Crc
            // using the setCrc()
            // function
            entry.setCrc(-1);

            // get the Crc
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
invalid entry crc-32

```

**函数抛出错误**

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/zip/ZipEntry . html # setCRc-long-](https://docs.oracle.com/javase/8/docs/api/java/util/zip/ZipEntry.html#setCrc-long-)