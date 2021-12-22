# Java 中的平减器 getBytesRead()函数，示例

> 原文:[https://www . geesforgeks . org/pincer-getbytesread-function-in-Java-with-examples/](https://www.geeksforgeeks.org/deflater-getbytesread-function-in-java-with-examples/)

在 **java.util.zip** 中**平减器类**的 **getBytesRead()** 函数返回到目前为止提供的未压缩字节输入的总数。

**功能签名:**

```
public long getBytesRead()

```

**语法:**

```
d.getBytesRead();

```

**参数:**函数不需要参数

**返回类型:**该函数返回一个**长值**，这是输入的未压缩字节总数。

**异常:**函数不抛出任何异常

**例 1:**

```
// Java program to describe the use
// of getBytesRead() function

import java.util.zip.*;
import java.io.UnsupportedEncodingException;

class GFG {
    public static void main(String args[])
        throws UnsupportedEncodingException
    {
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

        // compressed String
        System.out.println("Compressed String :"
                           + new String(output)
                           + "\n Size " + size);

        // original String
        System.out.println("Original String :"
                           + text + "\n Size "
                           + text.length());

        // get the total number of
        // uncompressed bytes input so far
        System.out.println("Bytes Read value :"
                           + d.getBytesRead());

        // end
        d.end();
    }
}
```

**输出:**

```
Compressed String :x?sOM?.N?/r???q??
 Size 21
Original String :GeeksforGeeksGeeksforGeeksGeeksforGeeksGeeksforGeeks
 Size 52
Bytes Read value :52

```

![](img/9dd0cb3afb9bb93de704d0bec4982157.png)

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/zip/pincher . html # getBytesRead()](https://docs.oracle.com/javase/7/docs/api/java/util/zip/Deflater.html#getBytesRead())