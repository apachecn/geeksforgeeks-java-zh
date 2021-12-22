# Java 中的 CharsetEncoder malformedingputaction()方法，示例

> 原文:[https://www . geeksforgeeks . org/charsetencoder-malformedinputation-method-in-Java-with-examples/](https://www.geeksforgeeks.org/charsetencoder-malformedinputaction-method-in-java-with-examples/)

**malformedinputation()**方法是**Java . nio . charset . charset encoder**的内置方法，返回该编码器当前针对格式错误输入错误的操作。这样返回的 CodingErrorAction 有三种类型:IGNORE、REPLACE 和 REPORT。

**语法** :

```
public CodingErrorAction malformedInputAction()
```

**参数**:该功能不接受任何参数。

**返回值**:函数返回当前的畸形输入动作，永不为空。

下面是上述功能的实现:

**程序 1:**

```
// Java program to implement
// the above function
import java.nio.CharBuffer;
import java.nio.charset.Charset;
import java.nio.charset.CharsetEncoder;

public class Main {
    public static void main(String[] args) throws Exception
    {
        // Gets the encoder
        CharsetEncoder encoder = Charset.forName("UTF16").newEncoder();

        // Prints CodingErrorAction
        System.out.println(encoder.malformedInputAction());
    }
}
```

**输出:**

```
REPORT

```

**程序二:**

```
// Java program to implement
// the above function
import java.nio.CharBuffer;
import java.nio.charset.Charset;
import java.nio.charset.CharsetEncoder;

public class Main {
    public static void main(String[] args) throws Exception
    {
        // Gets the encoder
        CharsetEncoder encoder = Charset.forName("US-ASCII").newEncoder();

        // Prints CodingErrorAction
        System.out.println(encoder.malformedInputAction());
    }
}
```

**输出:**

```
REPORT

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/nio/charset/charsetencoder . html # malformedinputation()](https://docs.oracle.com/javase/10/docs/api/java/nio/charset/CharsetEncoder.html#malformedInputAction())