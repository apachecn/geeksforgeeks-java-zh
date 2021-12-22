# Java 中的打气筒 getTotalIn()函数，带示例

> 原文:[https://www . geeksforgeeks . org/dugger-gettotalin-function-in-Java-with-examples/](https://www.geeksforgeeks.org/inflater-gettotalin-function-in-java-with-examples/)

**充气器类**的**gettotallin()**功能返回到目前为止提供的压缩字节输入总数。

**功能签名:**

```java
public int getTotalIn()

```

**语法:**

```java
i.getTotalIn();

```

**参数:**函数不需要参数

**返回类型:**函数返回 int 值，即输入的压缩字节总数。

**异常:**函数不抛出任何异常

**示例 1:**getTotalIn()函数的使用

```java
// Java program to describe the use
// of getTotalIn() function

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

        // get the total number of compressed bytes input so far
        System.out.println("Total Input value :" + i.getTotalIn());

        // end
        i.end();
    }
}
```

**输出:**
![](img/c12874d2bd8bbbc68b16216c8e378951.png)

****注意:**当输入的长度大于 Integer 时会出现问题。MAX_VALUE 那么结果可能会溢出，我们应该用 getBytesRead()函数来代替**

 ****引用:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/zip/fluger . html # getTotalIn()](https://docs.oracle.com/javase/7/docs/api/java/util/zip/Inflater.html#getTotalIn())**