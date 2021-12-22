# Java 中的打气筒 setInput()函数，示例

> 原文:[https://www . geeksforgeeks . org/dugger-set input-function-in-Java-with-examples/](https://www.geeksforgeeks.org/inflater-setinput-function-in-java-with-examples/)

使用**充气器类**的**设置输入()**功能来设置要解压缩的输入数据。当 needsInput()返回 true 表示输入缓冲区为空时，应调用此函数。

**功能签名:**

```java
public void setInput(byte[] b)
public void setInput(byte[] b, int offset, int len)

```

**语法:**

```java
i.setInput(byte[]);
i.setInput(byte[], int, int);

```

**参数:**这些重载函数接受的各种参数有:

*   **字节【】b** :这是要膨胀的输入数组
*   **int offset** :这是给定数组中读取值的起始偏移量
*   **int length** :这是从起始偏移量开始压缩的最大长度。

**返回类型:**函数没有返回值

**异常:**函数不抛出任何异常

**示例 1:**setInput(字节[] b)函数的使用

```java
// Java program to describe the use
// of setInput(byte[] b) function

import java.util.zip.*;
import java.io.UnsupportedEncodingException;
class GFG {
    public static void main(String args[])
        throws UnsupportedEncodingException,
               DataFormatException
    {

        // compress the data

        // deflater
        Deflater d = new Deflater();

        // get the text
        String pattern = "GeeksforGeeks", text = "";

        // generate the text
        for (int i = 0; i < 4; i++)
            text += pattern;

        // set the input for deflator
        d.setInput(text.getBytes("UTF-8"));

        // finish
        d.finish();

        // output bytes
        byte output[] = new byte[1024];

        // compress the data
        int size = d.deflate(output);

        // end
        d.end();

        // end of compression

        // use Inflater to get back the original data

        // Inflater
        Inflater i = new Inflater();

        // set the input for inflator
        i.setInput(output);

        // output bytes
        byte inflater_output[] = new byte[1024];

        // uncompress the data
        int org_size = i.inflate(inflater_output);

        // output of inflater and deflater
        System.out.println("Compressed output of deflater : "
                           + new String(output));
        System.out.println("Compressed output of Inflater : "
                           + new String(inflater_output, "UTF-8"));

        // end
        i.end();
    }
}
```

**输出:**
![](img/7231bf812ef9febe535b47366118c8c9.png)

**示例 2:**setInput(byte[]b，int offset，int len)函数的使用

```java
// Java program to describe the use
// of setInput(byte[] b, int offset, int len) function

import java.util.zip.*;
import java.io.UnsupportedEncodingException;
class GFG {
    public static void main(String args[])
        throws UnsupportedEncodingException,
               DataFormatException
    {

        // compress the data

        // deflater
        Deflater d = new Deflater();

        // get the text
        String pattern = "GeeksforGeeks", text = "";

        // generate the text
        for (int i = 0; i < 4; i++)
            text += pattern;

        // set the input for deflator
        d.setInput(text.getBytes("UTF-8"));

        // finish
        d.finish();

        // output bytes
        byte output[] = new byte[1024];

        // compress the data
        int size = d.deflate(output);

        // end
        d.end();

        // end of the compression

        // use Inflater to get back the original data

        // Inflater
        Inflater i = new Inflater();

        // set the input for inflator
        i.setInput(output, 0, 14);

        // output bytes
        byte inflater_output[] = new byte[1024];

        // uncompress the data
        int org_size = i.inflate(inflater_output);

        // output of inflater and deflater
        System.out.println("Compressed output of deflater : "
                           + new String(output));
        System.out.println("Compressed output of Inflater : "
                           + new String(inflater_output, "UTF-8"));

        // end
        i.end();
    }
}
```

**输出:**
![](img/c6dc36bce07e38c9d4b3fb2e18db4f5f.png)

 **参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/zip/ugger . html # setInput()](https://docs.oracle.com/javase/7/docs/api/java/util/zip/Inflater.html#setInput())