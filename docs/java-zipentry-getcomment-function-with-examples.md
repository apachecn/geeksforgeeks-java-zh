# Java zipcentry getComment()函数示例

> 原文:[https://www . geeksforgeeks . org/Java-zipper entry-getcomment-function-with-examples/](https://www.geeksforgeeks.org/java-zipentry-getcomment-function-with-examples/)

函数是 java.util.zip 包的一部分。该函数返回特定 ZipEntry 的注释。
**功能签名:**

```java
public String getComment()
```

**语法:**

```java
zip_entry.getComment();
```

**参数:**该功能不需要参数。
**返回值:**该函数返回 String 对象，即这个 ZipEntry 的注释。
**异常:**函数不抛出任何异常。

**以下程序说明了 getComment()功能的使用**

**示例 1:** 我们将创建一个名为 zip_file 的文件，并使用 getEntry()函数获取 zip 文件条目，然后获取指定 ZipEntry 的注释。“file.zip”是 f:目录中的一个 zip 文件。

```java
// Java program to demonstrate the
// use of getComment() function

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

            // get the Comment
            // using the getComment()
            // function
            String input = entry.getComment();

            // Display the comment
            System.out.println("Comment : " + input);
        }
        catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**Output:**

```java
Comment : This is a Zip Entry comment

```

**示例 2:** 我们将创建一个名为 zip_file 的文件，并使用 getEntry()函数获取 zip 文件条目，然后获取指定 ZipEntry 的注释。“file.zip”是 f:目录中的一个 zip 文件。
未设置评论时。

```java
// Java program to demonstrate the
// use of getComment() function

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

            // get the Comment
            // using the getComment()
            // function
            String input = entry.getComment();

            // Display the comment
            System.out.println("Comment : " + input);
        }
        catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**Output:**

```java
Comment : null

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/zip/ZipEntry . html # GetComment–](https://docs.oracle.com/javase/9/docs/api/java/util/zip/ZipEntry.html#getComment--)