# 打气筒用 Java 完成了()函数，示例

> 原文:[https://www . geeksforgeeks . org/dugger-finished-function-in-Java-with-examples/](https://www.geeksforgeeks.org/inflater-finished-function-in-java-with-examples/)

如果压缩数据流已经结束，则**充气器类**的**完成()**功能返回真。

**功能签名:**

```java
public boolean finished()

```

**语法:**

```java
i.finished();

```

**参数:**函数不需要参数

**返回类型:**该函数返回布尔值，如果所有输入都是未压缩的并存储在给定的缓冲区中，则返回 true，否则返回 false。

**异常:**函数不抛出任何异常

**例 1:** 成品功能的使用

```java
// Java program to describe the use
// of finished() function

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

        // value returned by finished function
        System.out.println("end of compressed data stream reached :"
                           + i.finished());

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

        // value returned by finished function
        System.out.println("end of compressed data stream reached :"
                           + i.finished());

        // end
        i.end();
    }
}
```

**输出:**
![](img/8829d0a6916b14810e525dbcde9529ff.png)

 **参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/zip/ugger . html # finished()](https://docs.oracle.com/javase/7/docs/api/java/util/zip/Inflater.html#finished())