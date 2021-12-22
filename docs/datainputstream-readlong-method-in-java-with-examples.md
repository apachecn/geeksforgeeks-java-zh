# Java 中的 DataInputStream readLong()方法，带示例

> 原文:[https://www . geesforgeks . org/datainputstream-readlong-method-in-Java-with-examples/](https://www.geeksforgeeks.org/datainputstream-readlong-method-in-java-with-examples/)

Java 中 **DataInputStream** 类的 **readLong()** 方法用于读取 8 个输入字节并返回一个长值。此方法从输入流中读取接下来的八个字节，并将其解释为长类型，然后返回。

**语法:**

```
public final long readLong()
                  throws IOException

```

**指定者:**该方法由**数据输入**界面的 readLong()方法指定。

**参数:**此方法不接受任何参数。

**返回值:**该方法返回输入流接下来 8 个字节解释的长值。

**异常:**

*   **eofeexception**–如果输入流在读取 8 个字节之前结束，它将抛出**eofeexception**。
*   **IOException**–如果流关闭或发生其他输入/输出错误，该方法将抛出 **IOException** 。

下面的程序说明了 IO 包中 DataInputStream 类的 readLong()方法:

**程序 1:** 假设存在文件“demo.txt”。

```
// Java program to illustrate
// DataInputStream readLong() method
import java.io.*;
public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // Create long array
        long[] buf = { 10000000000l,
                       20000000000l,
                       30000000000l };

        // Create file output stream
        FileOutputStream outputStream
            = new FileOutputStream("c:\\demo.txt");

        // Create data output stream
        DataOutputStream dataOutputStr
            = new DataOutputStream(outputStream);

        for (long b : buf) {
            // Write long value to
            // the dataOutputStream
            dataOutputStr.writeLong(b);
        }

        dataOutputStr.flush();

        // Create file input stream
        FileInputStream inputStream
            = new FileInputStream("c:\\demo.txt");

        // Create data input stream
        DataInputStream dataInputStr
            = new DataInputStream(inputStream);

        while (dataInputStr.available() > 0) {
            // Print long values
            System.out.println(
                dataInputStr.readLong());
        }
    }
}
```

**Output:**[![](img/eb150fb9f28512aa38ad2545522a5e16.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200601162223/long-1.png)

**程序 2:** 假设文件“demo.txt”的存在。

```
// Java program to illustrate
// DataInputStream readLong() method
import java.io.*;
public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // Create long array
        long[] buf = { 1234567890L,
                       9876543210L,
                       12345678910L };

        // Create file output stream
        FileOutputStream outputStream
            = new FileOutputStream("c:\\demo.txt");

        // Create data output stream
        DataOutputStream dataOutputStr
            = new DataOutputStream(outputStream);

        for (long b : buf) {
            // Write long value to
            // the dataOutputStream
            dataOutputStr.writeLong(b);
        }

        dataOutputStr.flush();

        // Create file input stream
        FileInputStream inputStream
            = new FileInputStream("c:\\demo.txt");

        // Create data input stream
        DataInputStream dataInputStr
            = new DataInputStream(inputStream);

        while (dataInputStr.available() > 0) {
            // Print long values
            System.out.println(
                dataInputStr.readLong());
        }
    }
}
```

**Output:**[![](img/49700640afc5ffe8fab101a2e2f483d2.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200601162242/long-2.png)

**参考资料:**
[https://docs . Oracle . com/javae/10/docs/API/Java/io/datainputstream . html # readlong()](https://docs.oracle.com/javase/10/docs/api/java/io/DataInputStream.html#readLong())