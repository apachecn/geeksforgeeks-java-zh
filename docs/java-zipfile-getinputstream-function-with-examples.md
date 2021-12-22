# Java ZipFile getInputStream()函数示例

> 原文:[https://www . geesforgeks . org/Java-zipfile-getinputstream-function-with-examples/](https://www.geeksforgeeks.org/java-zipfile-getinputstream-function-with-examples/)

getInputStream()函数是 java.util.zip 包的一部分。该函数返回作为参数传递的特定 ZipEntry 的 InputStream。关闭压缩文件也将关闭该函数生成的所有输入流。
**功能签名:**

```
public InputStream getInputStream(ZipEntry e)
```

**语法:**

```
zip_file.getInputStream(entry);
```

**参数:**该函数以一个 ZipEntry 对象为参数。
**返回值:**该函数返回一个 InputStream 对象来读取 ZipFile 条目的内容。
**例外:**

*   如果压缩文件已经关闭，该函数将抛出**illegalstatexception***   如果出现压缩格式错误，该函数将抛出**压缩异常***   The function throws **IOException** if an I/O error has occurred

    **下面的程序说明了 getInputStream()函数的使用**

    **示例 1:** 我们将创建一个名为 zip_file 的文件，并使用 getEntry()函数获取 zip 文件条目，然后获取 Input Stream 对象来读取文件的内容。“file.zip”是 f:目录中的一个 zip 文件。

    ```
    // Java program to demonstrate the
    // use of getInputStream() function

    import java.util.zip.*;
    import java.util.Enumeration;
    import java.util.*;
    import java.io.*;

    public class solution {
        public static void main(String args[])
        {
            try {
                // Create a Zip File
                ZipFile zip_file = new ZipFile("f:\\file.zip");

                // get the Zip Entry using
                // the getEntry() function
                ZipEntry entry = zip_file.getEntry("file1.cpp");

                // get the Input Stream
                // using the getInputStream()
                // function
                InputStream input = zip_file.getInputStream(entry);

                // Create a scanner object
                Scanner sc = new Scanner(input);

                System.out.println("Contents:");

                // Display the contents Zip Entry
                while (sc.hasNext()) {
                    System.out.println(sc.nextLine());
                }

                // Close the scanner
                sc.close();
            }
            catch (Exception e) {
                System.out.println(e.getMessage());
            }
        }
    }
    ```

    **Output:**

    ```
    Contents:
    This is a file in ZIP file.

    ```

    **示例 2:** 我们将创建一个名为 zip_file 的文件，并使用 getEntry()函数获取 zip 文件条目，然后获取 Input Stream 对象来读取文件的内容。zip 文件中不存在“file4.cpp”。

    ```
    // Java program to demonstrate the
    // use of getInputStream() function

    import java.util.zip.*;
    import java.util.Enumeration;
    import java.util.*;
    import java.io.*;

    public class solution {
        public static void main(String args[])
        {
            try {
                // Create a Zip File
                ZipFile zip_file = new ZipFile("f:\\file.zip");

                // get the Zip Entry using
                // the getEntry() function
                ZipEntry entry = zip_file.getEntry("file4.cpp");

                // Get the Input Stream
                // using the getInputStream()
                // function
                InputStream input = zip_file.getInputStream(entry);

                // Create a scanner object
                Scanner sc = new Scanner(input);

                System.out.println("Contents:");

                // Display the contents Zip Entry
                while (sc.hasNext()) {
                    System.out.println(sc.nextLine());
                }

                // Close the scanner
                sc.close();
            }
            catch (Exception e) {
                System.out.println(e.getMessage());
            }
        }
    }
    ```

    **Output:**

    ```
    null

    ```

    **函数抛出错误。**

    **参考:**[https://docs . Oracle . com/javae/7/docs/API/Java/util/zip/zipfile . html # getinpertstream(Java . util . zip . zipentry)](https://docs.oracle.com/javase/7/docs/api/java/util/zip/ZipFile.html#getInputStream(java.util.zip.ZipEntry))