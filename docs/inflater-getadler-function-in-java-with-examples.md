# Java 中的打气筒 getAdler()函数，示例

> 原文:[https://www . geeksforgeeks . org/dugger-getadler-function-in-Java-with-examples/](https://www.geeksforgeeks.org/inflater-getadler-function-in-java-with-examples/)

**增压泵类**的 **getAdler()** 功能返回未压缩数据的 **Adler-32** 值。 [Adler-32](https://en.wikipedia.org/wiki/Adler-32) 是 zlib 压缩库中广泛使用的校验和算法。

**功能签名:**

```
public int getAdler()

```

**语法:**

```
i.getAdler();

```

**参数:**函数不需要参数

**返回类型:**该函数返回**整数值**，这是未压缩数据的阿德勒-32 值。
**异常:**函数不抛出任何异常

**示例 1:**getAdler()函数的使用

```
// Java program to describe the use
// of getAdler function

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

        // get Adler-32 value
        System.out.println("Adler-32 value :" + i.getAdler());

        // end
        i.end();
    }
}
```

**输出:**
![](img/343fa14eb98f1e335e66aaf8fa213a3c.png)

 **参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/zip/fluger . html # getAdler()](https://docs.oracle.com/javase/7/docs/api/java/util/zip/Inflater.html#getAdler())