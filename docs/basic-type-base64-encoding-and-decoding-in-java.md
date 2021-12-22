# Java 基本类型 Base64 编解码

> 原文:[https://www . geesforgeks . org/basic-type-base64-Java 编码和解码/](https://www.geeksforgeeks.org/basic-type-base64-encoding-and-decoding-in-java/)

**Base 64** 是一种将二进制数据转换为文本格式的编码方案，因此编码后的文本数据可以轻松地在网络上传输，不会损坏，也不会丢失任何数据。 [(Base 64 格式参考)](https://www.geeksforgeeks.org/encode-ascii-string-base-64-format/)。
基本编码意味着输出中不添加换行，输出被映射到 A-Za-z0-9+/字符集内的一组字符，解码器拒绝该字符集以外的任何字符。
**将简单字符串编码为基本基本 64 格式**

> 字符串 basicbase 64 format = base64 . get ncoder()。encodetectstring(" actualring ")。getbytes()；

**解释:**在上面的代码中我们称之为 Base64。使用 getEncoder()进行编码，然后通过将 encodeToString()方法中的 actualString 的字节值作为参数传递来获取编码后的字符串。
**将基本 Base 64 格式解码为字符串**

> 字节[]当前字节= Base64.getDecoder()。解码器(encodedstring)；
> 字符串 current string =新字符串(当前字节)；

**解释:**在上面的代码中我们称之为 Base64。解码器使用 getDecoder()然后解码在 decode()方法中作为参数传递的字符串，然后将返回值转换为字符串。
下面的程序说明了 Java 中的编码和解码:
**程序 1:** 将简单字符串编码为 Basic Base 64 格式

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Encoding simple String into Basic Base 64 format

import java.util.*;
public class GFG {
    public static void main(String[] args)
    {

        // create a sample String to encode
        String sample = "India Team will win the Cup";

        // print actual String
        System.out.println("Sample String:\n"
                           + sample);

        // Encode into Base64 format
        String BasicBase64format
            = Base64.getEncoder()
                  .encodeToString(sample.getBytes());

        // print encoded String
        System.out.println("Encoded String:\n"
                           + BasicBase64format);
    }
}
```

**Output:** 

```java
Sample String:
India Team will win the Cup
Encoded String:
SW5kaWEgVGVhbSB3aWxsIHdpbiB0aGUgQ3Vw
```

**程序 2:** 将基本基本 64 格式解码为字符串

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Decoding Basic Base 64 format to String

import java.util.*;
public class GFG {
    public static void main(String[] args)
    {

        // create an encoded String to decode
        String encoded
            = "SW5kaWEgVGVhbSB3aWxsIHdpbiB0aGUgQ3Vw";

        // print encoded String
        System.out.println("Encoded String:\n"
                           + encoded);

        // decode into String from encoded format
        byte[] actualByte = Base64.getDecoder()
                                .decode(encoded);

        String actualString = new String(actualByte);

        // print actual String
        System.out.println("actual String:\n"
                           + actualString);
    }
}
```

**Output:** 

```java
Encoded String:
SW5kaWEgVGVhbSB3aWxsIHdpbiB0aGUgQ3Vw
actual String:
India Team will win the Cup
```

**参考文献:**

*   [https://docs . Oracle . com/javae/10/docs/API/Java/util/base 64 . html # get ncoder()](https://docs.oracle.com/javase/10/docs/api/java/util/Base64.html#getEncoder())T2]
*   [https://docs . Oracle . com/javae/9/docs/API/Java/util/base 64 . html # get ecoder--](https://docs.oracle.com/javase/9/docs/api/java/util/Base64.html#getDecoder--)

*   [https://www . geeksforgeeks . org/decode-encoded-base-64-string-ascii-string/](https://www.geeksforgeeks.org/decode-encoded-base-64-string-ascii-string/)

*   [https://www . geesforgeks . org/encode-ascii-string-base-64-format/](https://www.geeksforgeeks.org/encode-ascii-string-base-64-format/)