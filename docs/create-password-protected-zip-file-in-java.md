# 用 Java 创建密码保护的 Zip 文件

> 原文:[https://www . geesforgeks . org/create-密码保护-zip-file-in-java/](https://www.geeksforgeeks.org/create-password-protected-zip-file-in-java/)

首先，java 没有任何函数或包可以在不使用一些本机代码的情况下创建受密码保护的 zip 文件。Java 有一些有用的库，这很好，但是它们使用一些本机代码来执行它们的任务，这使得它们的使用在某种程度上依赖于平台。而在 zip4j 库中，我们只使用 java 代码，不支持任何本机代码，这就是人们使用 jip4j 胜过其他内置库的原因。

有一个名为‘zip4j’的库，是由*Srikanth Reddy Lingala*在 2008/2009 年写的。它是针对 zip 文件的最全面的 Java 库。

zip4j 库的一些重要特性如下:

1.  它将创建、添加、提取、更新、删除 zip 文件中的文件。
2.  它支持类似[的子输入流](https://www.geeksforgeeks.org/java-util-zip-zipinputstream-class-java/)和[的子输出流](https://www.geeksforgeeks.org/java-util-zip-zipoutputstream-class-java/)。
3.  我们可以使用这个库在 java 中创建任何受密码保护的 zip 文件。
4.  我们可以通过指定文件路径来压缩/解压缩任何现有的文件或目录。
5.  它还支持 AES 128/256 加密和标准 Zip 加密。

> **注意:‘**zip4j’是在 JDK 8 上写的，如果我们尝试在 JDK 7 上运行这个库，那么并不是所有的特性都会被支持。

**方法:**

1.  使用 java.util.zip 包的简单方法
2.  高效方法

**方法 1:** 天真方法

我们没有任何标准的 java 内置库来创建密码保护的 zip 文件。我们只能借助 *java.util.zip* 包制作一个简单的 zip 文件。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Create Password Protected Zip File

// Importing all input output classes
import java.io.*;
// Importing java.nio utility package API
// used for manipulating files and directories
// mostly working on Path object
import java.nio.file.*;
// Importing all zip classes from
// java.util package
import java.util.zip.*;

// Class
// Main class
public class ZipFile {

// Method 1
 // Creating an existing file as a zip file
    private static void zipFile(String filePath) {

        // Try block  to check if any exception occurs
        try {

            // Creating an object of File type
            // getting filePath by passing as an argument
            File file = new File(filePath);

            // Getting the name of the above file
            // as an ZIP format
            String zipFileName = file.getName().concat(".zip");

            // Creating FileOutputStream object and passing the
            // zip file as an argument
            FileOutputStream fos = new FileOutputStream(zipFileName);

            // Creating sn object of FileOutputStream and
            // passing the above object as an argument
            ZipOutputStream zos = new ZipOutputStream(fos);

            zos.putNextEntry(new ZipEntry(file.getName()));

            // Writing the ZipEntry to stream is not enough
            // as we need to write its content as well
            // using the putNextEntry() method
            byte[] bytes = Files.readAllBytes(Paths.get(filePath));
            zos.write(bytes, 0, bytes.length);

            // ZipFile can only hold 1 entry stream at a go, &
            // if another entry is to be passed then
            // current entry stream has to be closed closeEntry

            // Closing the current entry stream
            // using the closeEntry() method
            zos.closeEntry();

            // Closing the entire stream completely
            zos.close();

        // If file does not find then it will return the file does not exist
        }

        // Catch block 1
        // Catch block to handle FieNotFoundException
        catch (FileNotFoundException ex) {

            // Print and display message
            System.err.format("The file does not exist", filePath);
        }

        // Catch block 2
        // Catch block to handle input output exception
        catch (IOException ex) {

            // Print and display message 
            System.err.println("ERROR: " + ex);
        }
    }

    // Method 2
    // Main driver method
    public static void main(String[] args) {

        String filePath = args[0];

        // Calling the above method 1
        zipFile(filePath);

    }
}
```

**方法 2:** 高效方法

**程序:**

1.  首先，创建一个要添加到 ZIP 文件的文件列表
2.  指定可以将其添加到列表中的路径。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Create Password Protected Zip File

// Importing required  libraries
// Here, lingala is the name of men
// who created zip4j library
import java.io.File;
import java.util.ArrayList;
import net.lingala.zip4j.core.ZipFile;
import net.lingala.zip4j.exception.ZipException;
import net.lingala.zip4j.model.ZipParameters;
import net.lingala.zip4j.util.Zip4jConstants;

// Class
// To create password protected ZIP file
public class GFG {

    // Main driver method
    public static void main(String[] args) {

           // Try block to check if any exception occurs
           try {

                  // Creating encryption zipParameters
                  // for passward protection
                  ZipParameters zipParameters = new ZipParameters();

                  // Setting encryption files
                  zipParameters.setCompressionMethod(Zip4jConstants.COMP_DEFLATE);
                  zipParameters.setCompressionLevel(Zip4jConstants.DEFLATE_LEVEL_NORMAL);

                  // Setting encryption of files to true
                  zipParameters.setEncryptFiles(true);

                  // Setting encryption method
                  zipParameters.setEncryptionMethod(Zip4jConstants.ENC_METHOD_AES);

                  // Set the key strength
                  zipParameters.setAesKeyStrength(Zip4jConstants.AES_STRENGTH_256);

                  // Set the password
                  zipParameters.setPassword("password");

                  // *********CREATE ZIP FILE***************

                  //Zip file name
                  String destinationZipFilePath = "D:/myZipFile.zip";

                  // Creating ZIP file
                  ZipFile zipFile = new ZipFile(destinationZipFilePath);

                  // Creating list of files to be added to ZIP file
                  ArrayList<File> list = new ArrayList<File>();
                  //Add SPECIFIC  files
                  list.add(new File("D:/myFile1.txt"));
                  list.add(new File("D:/myFile2.txt"));

                  // Pass and ZIP parameters
                  // for Zip file to be created
                  zipFile.addFiles(list, zipParameters);

                  // Print the destination in the local directory
                  // where ZIP file is created
                  System.out.println("Password protected Zip file"
                               + "have been created at "  + destinationZipFilePath);

            // Catch block to handle the exceptions
           } catch (ZipException e) {

                  // Print the exception and line number
                  // where tit occured 
                  e.printStackTrace();
           }
    }
}
```