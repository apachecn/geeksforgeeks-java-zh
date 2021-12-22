# Java 中的 DataInputStream readFloat()方法，带示例

> 原文:[https://www . geesforgeks . org/datainputstream-readfloat-method-in-Java-with-examples/](https://www.geeksforgeeks.org/datainputstream-readfloat-method-in-java-with-examples/)

Java 中 **DataInputStream** 类的 **readFloat()** 方法用于读取四个输入字节并返回一个 Float 值。此方法从输入流中读取接下来的四个字节，并将其解释为浮点类型，然后返回。

**语法:**

```
public final float readFloat()
                  throws IOException

```

**指定者:**该方法由**数据输入**界面的 readFloat()方法指定。

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回由输入流的下四个字节解释的浮点值。

**异常:**

*   **eofeexception**–如果输入流在读取四个字节之前结束，它将抛出**eofeexception**。
*   **IOException**–如果流关闭或发生其他输入/输出错误，该方法将抛出 **IOException** 。

下面的程序说明了 IO 包中 DataInputStream 类中的 readFloat()方法:

**程序 1:** 假设存在文件“demo.txt”。

```
// Java program to illustrate
// DataInputStream readFloat() method
import java.io.*;
public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // Create float array
        float[] buf = { 10, 20, 30, 40, 50 };

        // Create file output stream
        FileOutputStream outputStream
            = new FileOutputStream("c:\\demo.txt");

        // Create data output stream
        DataOutputStream dataOutputStr
            = new DataOutputStream(outputStream);

        for (float b : buf) {
            // Write float value to
            // the dataOutputStream
            dataOutputStr.writeFloat(b);
        }

        dataOutputStr.flush();

        // Create file input stream
        FileInputStream inputStream
            = new FileInputStream("c:\\demo.txt");

        // Create data input stream
        DataInputStream dataInputStr
            = new DataInputStream(inputStream);

        while (dataInputStr.available() > 0) {
            // Print float values
            System.out.println(
                dataInputStr.readFloat());
        }
    }
}
```

**Output:**[![](img/a933b626c20a7bd54c4899d5d1462466.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200601125308/data_double-1.png)

**程序 2:** 假设文件“demo.txt”的存在。

```
// Java program to illustrate
// DataInputStream readFloat() method
import java.io.*;
public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // Create float array
        float[] buf = { 10.9f, 20.8f,
                        30.88f, 40.76f,
                        50.678f };

        // Create file output stream
        FileOutputStream outputStream
            = new FileOutputStream("c:\\demo.txt");

        // Create data output stream
        DataOutputStream dataOutputStr
            = new DataOutputStream(outputStream);

        for (float b : buf) {
            // Write float value to
            // the dataOutputStream
            dataOutputStr.writeFloat(b);
        }

        dataOutputStr.flush();

        // Create file input stream
        FileInputStream inputStream
            = new FileInputStream("c:\\demo.txt");

        // Create data input stream
        DataInputStream dataInputStr
            = new DataInputStream(inputStream);

        while (dataInputStr.available() > 0) {
            // Print float values
            System.out.println(
                dataInputStr.readFloat());
        }
    }
}
```

**Output:**[![](img/565f87db08fa05999ddf7b01c37008ad.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200601125334/data_double-2.png)

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/io/datainputstream . html # readFloat()](https://docs.oracle.com/javase/10/docs/api/java/io/DataInputStream.html#readFloat())