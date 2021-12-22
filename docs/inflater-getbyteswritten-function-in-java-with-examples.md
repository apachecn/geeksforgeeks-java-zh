# 打气筒 getBytesWritten()函数用 Java 举例

> 原文:[https://www . geeksforgeeks . org/dugger-getbytes written-function-in-Java-with-examples/](https://www.geeksforgeeks.org/inflater-getbyteswritten-function-in-java-with-examples/)

**充气器类**的 **getBytesWritten()** 函数返回到目前为止提供的未压缩字节输出的总数。

**功能签名:**

```java
public long getBytesWritten()

```

**语法:**

```java
i.getBytesWritten();

```

**参数:**函数不需要参数

**返回类型:**函数返回 Long 值，即输出的未压缩字节总数。

**异常:**函数不抛出任何异常

**示例 1:**getbytes written()函数的使用

```java
// Java program to describe the use
// of getBytesWritten() function

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

        // get the total number of uncompressed bytes output so far
        System.out.println("Bytes Written value :"
                           + i.getBytesWritten());

        // end
        i.end();
    }
}
```

**输出:**
![](img/20c4b1b2bd10c88c149a1c788a1a691e.png)

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/zip/fluger . html # getbytes written()](https://docs.oracle.com/javase/7/docs/api/java/util/zip/Inflater.html#getBytesWritten())