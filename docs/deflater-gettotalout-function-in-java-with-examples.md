# Java 中的平减器 getTotalOut()函数，带示例

> 原文:[https://www . geeksforgeeks . org/pincher-gettotallout-function-in-Java-with-examples/](https://www.geeksforgeeks.org/deflater-gettotalout-function-in-java-with-examples/)

在 **java.util.zip** 中**平减器类**的**gettotallout()**函数返回到目前为止提供的压缩字节输出总数。

**功能签名:**

```java
public int getTotalOut()

```

**语法:**

```java
d.getTotalOut();

```

**参数:**函数不需要参数

**返回类型:**该函数返回一个**整数值**，这是输出的压缩字节总数。

**异常:**函数不抛出任何异常

**例 1:**

```java
// Java program to describe the use
// of getTotalOut() function

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

        // set the Input for deflator
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
        // compressed bytes Output so far
        System.out.println("Total Output value :"
                           + d.getTotalOut());

        // end
        d.end();
    }
}
```

**输出:**

```java
Compressed String :x?sOM?.N?/r???q??
 Size 21
Original String :GeeksforGeeksGeeksforGeeksGeeksforGeeksGeeksforGeeks
 Size 52
Total Output value :21

```

![](img/8f1370cb7535d7550571948276af6d82.png)

**注:** **输入长度大于<u>整数时出现问题。最大值</u>。那么结果可能会溢出，我们应该用 getBytesRead()函数代替**

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/zip/平减器. html # gettotallout()](https://docs.oracle.com/javase/7/docs/api/java/util/zip/Deflater.html#getTotalOut())