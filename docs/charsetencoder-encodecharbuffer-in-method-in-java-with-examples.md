# Java 中的 CharsetEncoder 编码(CharBuffer in)方法，示例

> 原文:[https://www . geeksforgeeks . org/charsetencoder-encodecharbuffer-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/charsetencoder-encodecharbuffer-in-method-in-java-with-examples/)

**编码(CharBuffer input)** 方法是**Java . nio . charset . charsetencoder**的内置方法，它将单个输入字符缓冲区剩余的内容编码到新分配的字节缓冲区。encode()方法本身实现了整个编码操作。如果操作正在进行，则不应调用此函数。
**语法** :

```java
public final ByteBuffer encode(CharBuffer input)
```

**参数**:该功能接受指定输入字符缓冲区的强制参数输入。
**返回值**:该函数返回一个新分配的包含编码操作结果的字节缓冲区。
**错误和异常:**函数抛出四个异常，描述如下:

*   *illegalstatexception*:如果编码操作已经在进行，则抛出。
*   *MalformedInputException* :如果从输入缓冲区当前位置开始的字符序列不是合法的十六位 Unicode 序列，并且当前格式错误的输入操作是 CodingErrorAction.REPORT，则会引发该异常。
*   *不可映射字符异常*:如果从输入缓冲区当前位置开始的字符序列不能映射到等效的字节序列，并且当前的不可映射字符操作是 CodingErrorAction，则会引发该异常。报告
*   字符编码异常

下面是上述功能的实现:
**程序一:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to implement
// the above function
import java.nio.CharBuffer;
import java.nio.charset.Charset;
import java.nio.charset.CharsetEncoder;

public class Main {
    public static void main(String[] args) throws Exception
    {

        // Gets the new encoder
        CharsetEncoder encoder = Charset.forName("UTF8").newEncoder();

        // Encodes
        String res = "gfggfg";
        System.out.println(encoder.encode(CharBuffer.wrap(res)));
    }
}
```

**Output:** 

```java
java.nio.HeapByteBuffer[pos=0 lim=6 cap=6]
```