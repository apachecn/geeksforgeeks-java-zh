# Java ZipEntry setComment()函数示例

> 原文:[https://www . geeksforgeeks . org/Java-zippentry-set comment-function-with-examples/](https://www.geeksforgeeks.org/java-zipentry-setcomment-function-with-examples/)

函数是 java.util.zip 包的一部分。该函数将特定 ZipEntry 的注释设置为指定的字符串。
注释的最大长度为 0xffff，如果字符串的长度大于 0xffff，则将考虑前 0xffff 个字符。
**功能签名:**

```java
public void setComment(String s)
```

**语法:**

```java
zip_entry.setComment(s);
```

**参数:**函数接受一个字符串对象作为参数。
**返回值:**函数不返回值。
**异常:**函数不抛出任何异常。

**以下程序说明了 setComment()功能的使用**

**示例 1:** 我们将创建一个名为 zip_file 的文件，并使用 getEntry()函数获取 zip 文件条目，然后设置指定 ZipEntry 的注释。“file.zip”是 f:目录中的一个 zip 文件。

```java
// Java program to demonstrate the
// use of setComment() function

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
            entry.setComment("This is a ZipEntry comment");

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
Comment : This is a Zip Entry comment)

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/zip/ZipEntry . html # setComment-Java . lang . string-](https://docs.oracle.com/javase/9/docs/api/java/util/zip/ZipEntry.html#setComment-java.lang.String-)