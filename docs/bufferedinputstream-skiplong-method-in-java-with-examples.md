# Java 中 BufferedInputStream 跳过(长)方法，示例

> 原文:[https://www . geeksforgeeks . org/bufferedinputstream-skip long-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bufferedinputstream-skiplong-method-in-java-with-examples/)

Java 中 **BufferedInputStream** 类的**跳过(长)**方法用于从缓冲的输入流中跳过 n 字节的数据。跳过的字节数作为长类型存储并返回。终止条件涉及以下两者之一:

*   要么读入一个字节数组直到 n 字节被覆盖，
*   当输入结束时，流被满足。

但是，如果传递了负值，则不会发生跳过。
**语法:**

```java
public long skip(long n)
```

**参数:**该方法接受长类型的 **n** ，表示需要从输入流中跳过的字节数。
**返回值:**此方法返回作为长类型跳过的字节数。
**异常:**如果该输入流已经通过调用 close()方法关闭，或者该流不支持查找，或者出现任何其他 I/O 错误，则该方法抛出 **IOException** 。
下面的程序说明了 IO 包中 BufferedInputStream 类中的 skip(long)方法:
**程序 1:** 假设文件“c:/demo.txt”的存在。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate
// BufferedInputStream skip(long) method
import java.io.*;
public class GFG {
    public static void main(String[] args)
    {

        // Create input stream 'demo.txt'
        // for reading containing text "GEEK"
        FileInputStream inputStream = 
        new FileInputStream("c:/demo.txt");

        // Convert inputStream to 
        // bufferedInputStream
        BufferedInputStream buffInputStr 
              = new BufferedInputStream(
                          inputStream);

        // Read until a single
        // byte is available
        while(buffInputStr.available()>0) {

            // Skip single byte from the stream
            buffInputStr.skip(1);

            // Read next available byte and
            // convert to char
            char c = (char) buffInputStr.read();

            // Print character
            System.out.print(" " + c);
         }
    }
}
```

**Output:** 

```java
 E K
```