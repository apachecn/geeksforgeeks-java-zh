# Java zipcentry setCreationTime()函数示例

> 原文:[https://www . geeksforgeeks . org/Java-zippentry-set creation ontime-function-with-examples/](https://www.geeksforgeeks.org/java-zipentry-setcreationtime-function-with-examples/)

setCreationTime()函数是 java.util.zip 包的一部分。该功能用于设置压缩条目的创建时间。该函数以文件时间对象为参数。
文件时间对象，表示子条目的创建时间。
**功能签名:**

```
public void setCreationTime(FileTime v)
```

**语法:**

```
zip_entry.setCreationTime(v);
```

**参数:**函数以 FileTime 对象为参数，即文件的创建时间。
**返回值:**函数不取任何参数
**异常:**如果时间为空，函数抛出**空指针异常**

**下面的程序说明了 setCreationTime()函数的使用**
**示例 1:** 我们将创建一个名为 zip_file 的文件，并使用 getEntry()函数获取 zip 文件条目，然后设置指定 ZipEntry 的 CreationTime。“file.zip”是 f:目录中的一个 zip 文件。我们就拍一张”。zip”文件作为 ZipEntry

```
// Java program to demonstrate the
// use of setCreationTime() function

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

            // set the CreationTime
            // using the setCreationTime()
            // function
            entry.setCreationTime(FileTime.fromMillis(100000));

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

```
CreationTime : 1970-01-01T00:01:40Z

```

**示例 2:** 我们将创建一个名为 zip_file 的文件，并使用 getEntry()函数获取 zip 文件条目，然后设置指定 ZipEntry 的 CreationTime。“file.zip”是 f:目录中的一个 zip 文件。我们将创建时间的值设置为空。我们就拍一张”。cpp "文件作为 ZipEntry

```
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

            // set the CreationTime
            // using the setCreationTime()
            // function
            entry.setCreationTime(null);

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

```
CreationTime :

```

**由于设置了空值**，程序因错误而终止

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/zip/ZipEntry . html # setCreationTime-Java . nio . file . attribute . file time-](https://docs.oracle.com/javase/8/docs/api/java/util/zip/ZipEntry.html#setCreationTime-java.nio.file.attribute.FileTime-)