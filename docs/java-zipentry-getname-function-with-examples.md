# Java zipcentry getName()函数带示例

> 原文:[https://www . geeksforgeeks . org/Java-zipper entry-getname-function-with-examples/](https://www.geeksforgeeks.org/java-zipentry-getname-function-with-examples/)

函数是 java.util.zip 包的一部分。该函数返回作为参数传递的特定 ZipEntry 的名称。
**功能签名:**

```java
public int getName()
```

**语法:**

```java
zip_entry.getName();
```

**参数:**该功能不需要参数。
**返回值:**该函数返回一个字符串值，即这个子条目的名称。
**异常:**函数不抛出任何异常。

**以下程序说明了 getName()功能的使用**

**示例 1:** 我们将创建一个名为 zip_file 的文件，并使用 getEntry()函数获取 zip 文件条目，然后获取指定 ZipEntry 的名称。“file.zip”是 f:目录中的一个 zip 文件。我们就拍一张”。zip”文件作为 ZipEntry

```java
// Java program to demonstrate the
// use of getName() function

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

            // Get the  Name
            // using the getName()
            // function
            int input = entry.getName();

            // Display the  Name
            System.out.println(" Name : " + input);
        }
        catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**输出:**

```java
 Name : file.zip

```

**示例 2:** 我们将创建一个名为 zip_file 的文件，并使用 getEntry()函数获取 zip 文件条目，然后获取指定 ZipEntry 的名称。“file.zip”是 f:目录中的一个 zip 文件。我们就拍一张”。cpp "文件作为 ZipEntry

```java
// Java program to demonstrate the
// use of getName() function

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

            // Get the  Name
            // using the getName()
            // function
            String input = entry.getName();

            // Display the  Name
            System.out.println(" Name : " + input);
        }
        catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**输出:**

```java
 Name : file1.cpp

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/zip/ZipEntry . html # getName–](https://docs.oracle.com/javase/8/docs/api/java/util/zip/ZipEntry.html#getName--)