# 使用 Java 将字节[]数组转换为文件

> 原文:[https://www . geesforgeks . org/convert-byte-array-to-file-using-Java/](https://www.geeksforgeeks.org/convert-byte-array-to-file-using-java/)

要将字节[]转换为文件 **[使用 String 类的 getBytes()](https://www.geeksforgeeks.org/java-lang-string-getbyte-java/)** 方法，简单的 **[write()](https://contribute.geeksforgeeks.org/java-io-outputstreamwriter-class-methods/)** 方法可以将该字节转换为文件。

**程序 1:** 将字符串转换为字节[]并写入文件。

```
// Java Program to convert
// byte array to file
import java.io.File;
import java.io.FileOutputStream;
import java.io.OutputStream;

public class GFG {

    // Path of a file
    static String FILEPATH = "";
    static File file = new File(FILEPATH);

    // Method which write the bytes into a file
    static void writeByte(byte[] bytes)
    {
        try {

            // Initialize a pointer
            // in file using OutputStream
            OutputStream
                os
                = new FileOutputStream(file);

            // Starts writing the bytes in it
            os.write(bytes);
            System.out.println("Successfully"
                               + " byte inserted");

            // Close the file
            os.close();
        }

        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }

    // Driver Code
    public static void main(String args[])
    {

        String string = "GeeksForGeeks"
                        + " - A Computer Science"
                        + " Portal for geeks";

        // Get byte array from string
        byte[] bytes = string.getBytes();

        // Convert byte array to file
        writeByte(bytes);
    }
}
```

**输出:**

```
Successfully byte inserted

```

**程序 2:** 在文件中写入整数、双精度、字符值(使用包装类)。

```
// Java Program to convert
// int, char and double into bytes
// and write it in a file

import java.io.File;
import java.io.FileOutputStream;
import java.io.OutputStream;

public class GFG {

    // Path of a file
    static String FILEPATH = "";
    static File file = new File(FILEPATH);

    // Method which write the bytes into a file
    static void writeByte(byte[] byteInt,
                          byte[] byteChar, byte[] byteDouble)
    {

        try {

            // Initialize a pointer in file using OutputStream
            OutputStream os = new FileOutputStream(file);

            // Starts writing the bytes in it

            // Write int value
            os.write(byteInt);

            // Write char value
            os.write(byteChar);

            // Write double value
            os.write(byteDouble);

            System.out.println("Successfully byte inserted");

            // Close the file
            os.close();
        }

        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }

    // Driver Code
    public static void main(String args[])
    {
        int num = 56;
        char ch = 's';
        double dec = 78.9;

        // Insert int value
        byte[] byteInt = Integer.toString(num).getBytes();

        // Insert char value
        byte[] byteChar = Character.toString(ch).getBytes();

        // Insert double value
        byte[] byteDouble = Double.toString(dec).getBytes();

        writeByte(byteInt, byteChar, byteDouble);
    }
}
```

**输出:**

```
Successfully byte inserted

```