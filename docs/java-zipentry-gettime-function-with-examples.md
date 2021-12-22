# Java zipcentry getTime()函数示例

> 原文:[https://www . geeksforgeeks . org/Java-zippentry-gettime-function-with-examples/](https://www.geeksforgeeks.org/java-zipentry-gettime-function-with-examples/)

函数是 java.util.zip 包的一部分。该函数返回作为参数传递的特定 ZipEntry 的上次修改时间。
该函数返回长值，表示 ZipEntry 的上次修改时间(文件上次修改时间)，如果没有指定上次修改时间，则返回-1。
如果从 ZIP 文件或 ZIP 文件格式的输入流中读取 ZIP 条目，则这是最后一次修改时间，否则从条目的日期和时间字段中读取最后一次修改时间。
**功能签名:**

```
public long getTime()
```

**语法:**

```
zip_entry.getTime();
```

**参数:**该功能不需要参数。
**返回值:**该函数返回长值，表示子条目的上次修改时间。
**异常:**函数不抛出任何异常。0

**下面的程序说明了 getTime()功能的使用**

**示例 1:** 我们将创建一个名为 zip_file 的文件，并使用 getEntry()函数获取 zip 文件条目，然后获取指定 ZipEntry 的 LastModifiedTime。“file.zip”是 f:目录中的一个 zip 文件。我们就拍一张”。zip”文件作为 ZipEntry

```
// Java program to demonstrate the
// use of getTime() function

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
            // using the getTime()
            // function
            long input = entry.getTime();

            // Display the LastModifiedTime
            System.out.println("LastModifiedTime : " + input);
        }
        catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**Output:**

```
LastModifiedTime : 1551033735858

```

**示例 2:** 我们将创建一个名为 zip_file 的文件，并使用 getEntry()函数获取 zip 文件条目，然后获取指定 ZipEntry 的 LastModifiedTime。“file.zip”是 f:目录中的一个 zip 文件。我们就拍一张”。cpp "文件作为 ZipEntry

```
// Java program to demonstrate the
// use of getTime() function

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
            // using the getTime()
            // function
            long input = entry.getTime();

            // Display the LastModifiedTime
            System.out.println("LastModifiedTime : " + input);
        }
        catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**Output:**

```
LastModifiedTime : 1544189602654

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/zip/ZipEntry . html # GetTime–](https://docs.oracle.com/javase/8/docs/api/java/util/zip/ZipEntry.html#getTime--)