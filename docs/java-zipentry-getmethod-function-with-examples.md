# Java ZipEntry getMethod()函数示例

> 原文:[https://www . geeksforgeeks . org/Java-zippentry-getmethod-function-with-examples/](https://www.geeksforgeeks.org/java-zipentry-getmethod-function-with-examples/)

函数 **getMethod()** 是 java.util.zip 包的一部分。该函数返回作为参数传递的特定 ZipEntry 的压缩方法，如果未指定，则返回-1。
**功能签名:**

```java
public int getMethod()
```

**语法:**

```java
zip_entry.getMethod();
```

**参数:**该功能不需要参数。
**返回值:**这个函数返回一个 int 值，这个 ZipEntry 的压缩方法，如果没有指定的话，返回-1。
**异常:**函数不抛出任何异常。

**下面的程序说明了 getMethod()函数的使用**

**示例 1:** 我们将创建一个名为 zip_file 的文件，并使用 getEntry()函数获取 zip 文件条目，然后获取指定 ZipEntry 的压缩方法。“file.zip”是 f:目录中的一个 zip 文件。我们就拍一张”。zip”文件作为 ZipEntry

```java
// Java program to demonstrate the
// use of getMethod() function

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

            // Get the compression method
            // using the getMethod()
            // function
            int input = entry.getMethod();

            // Display the compression method
            System.out.println("compression method : " + input);
        }
        catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**Output:**

```java
compression method : 8

```

**示例 2:** 我们将创建一个名为 zip_file 的文件，并使用 getEntry()函数获取 zip 文件条目，然后获取指定 ZipEntry 的压缩方法。“file.zip”是 f:目录中的一个 zip 文件。我们就拍一张”。cpp "文件作为 ZipEntry

```java
// Java program to demonstrate the
// use of getMethod() function

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

            // Get the compression method
            // using the getMethod()
            // function
            int input = entry.getMethod();

            // Display the compression method
            System.out.println("compression method : " + input);
        }
        catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**Output:**

```java
compression method : 8

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/zip/ZipEntry . html # GetMethod–](https://docs.oracle.com/javase/8/docs/api/java/util/zip/ZipEntry.html#getMethod--)