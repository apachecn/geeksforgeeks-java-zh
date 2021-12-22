# Java 中 ZipFile 和 ZipInputStream 的区别

> 原文:[https://www . geesforgeks . org/zip file-和-zipinputstream-in-java/](https://www.geeksforgeeks.org/difference-between-zipfile-and-zipinputstream-in-java/) 的区别

[Zip 文件](https://www.geeksforgeeks.org/difference-between-zip-and-rar/)基本上是一个归档文件，用来将所有文件压缩在一个地方。这样做减少了占用的内存空间，并使文件包的传输变得容易。[***zip inputstream***](https://www.geeksforgeeks.org/java-util-zip-zipinputstream-class-java/)用于读取 zip 中存在的 zip 文件中的文件条目。在 Java 中，有两个类，即***【ZipFile】***和[***ZipInputStream***](https://www.geeksforgeeks.org/java-util-zip-zipinputstream-class-java/)，用于读取 zip 文件中存在的文件条目。这两个类都在 java.util.zip 类中，并且这两个类都实现了可关闭的接口，因为它们在读取和提取 zip 文件时都非常有用。

[ZipFile 类](https://www.geeksforgeeks.org/zipfile-entries-function-in-java-with-examples/) 用于读取压缩成 zip 文件的文件。这个类提供了几种方法来访问 zip 文件中的条目。此外，还有其他几种方法也存在于这个类中，但这不是我们现在关心的问题。下面列出了一些如下:

*   [*zipentry getentry (string name)*](https://www.geeksforgeeks.org/zipfile-getentry-function-in-java-with-examples/) *:* *getentry ()* The function is part of the java.util.zip package. This function returns [zipentry](https://www.geeksforgeeks.org/java-util-zip-zipentry-class-java/) of the file existing in the zip file specified by the string parameter. This method is used to get the entry of the file whose file name is specified in the string parameter.
*   *[*inputstream get inputstream (zipentry entry)*](https://www.geeksforgeeks.org/java-zipfile-getinputstream-function-with-examples/) *:* This method is used to create an input stream to read the data of this entry (file).*
**   [*Enumerate <? Expanded Zipcentry > entries ()*](https://www.geeksforgeeks.org/zipfile-entries-function-in-java-with-examples/) *: this is a very important method for this class. This method is used to generate an enumeration of all entries, which can then be accessed individually in any order. Therefore, this method ensures the non-sequential access of files. We can also access only those files that we need, instead of extracting all the files.**

***实现:**这是我们访问 zip 文件类的方式:*

 *## Java

```java
// Java Program to illustrate extraction of
// Zip file

// Importing classes and modules
import java.io.BufferedInputStream;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.util.Enumeration;
import java.util.Scanner;
import java.util.zip.ZipEntry;
import java.util.zip.ZipFile;
import java.util.zip.ZipInputStream;

// save as file named GFG.java

// Class
public class GFG {

    // Step 1: Specify the file name
    // with path of the zip file

    // Custom directory from local directory
    // is passed as an argument
    public static String file_path
        = "C:\\Users\\Dipak\\Desktop\\j.zip";

    // Step 2: Specify the name of the file
    // present in the zip file to be accessed
    public static String file_name = "j/ritu.txt";

    // Also do remember that one can take input
    // for the file path and name
    // Using Zipinputstream method
    public static BufferedInputStream b;
    public static ZipInputStream z;

    // Zipinputsream()  method for implementation
    public static void zipinputstream() throws IOException
    {
        z = new ZipInputStream(b);
        ZipEntry e;

        // If condition holds true
        while (true) {

            // Read the next ZIP file entry positioning
            // the stream at beginning
            e = z.getNextEntry();

            if (e == null)
                break;
            if (e.getName().equals(file_name)) {
                // Display message
                System.out.println("file size is "
                                   + e.getSize()
                                   + " bytes");
            }
        }
    }

    // Main driver method
    public static void main(String[] args) throws Exception
    {

        b = new BufferedInputStream(
            new FileInputStream(file_path));

        // calling static method
        zipinputstream();
    }
}
```*