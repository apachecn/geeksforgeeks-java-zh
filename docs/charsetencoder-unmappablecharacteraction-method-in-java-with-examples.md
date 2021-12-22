# Java 中的 CharsetEncoder unappablecharactor action()方法，示例

> 原文:[https://www . geeksforgeeks . org/charsetencoder-unappablecharactor action-method-in-Java-with-examples/](https://www.geeksforgeeks.org/charsetencoder-unmappablecharacteraction-method-in-java-with-examples/)

**不可映射字符动作()**方法是**Java . nio . charset . charset encoder**的内置方法，返回该编码器当前不可映射字符错误的动作。CodingErrorAction 有三种类型:忽略、替换和报告。

**语法** :

```java
public CodingErrorAction unmappableCharacterAction()
```

**参数**:该功能不接受任何参数。

**返回值**:函数返回当前不可映射字符动作，永不为空。

下面是上述功能的实现:

**程序 1:**

```java
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
        System.out.println(encoder.unmappableCharacterAction());
    }
}
```

**输出:**

```java
REPORT

```

**程序二:**

```java
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
        System.out.println(encoder.unmappableCharacterAction());
    }
}
```

**输出:**

```java
REPORT

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/nio/charset/charset encoder . html # unappablecharactoraction()](https://docs.oracle.com/javase/10/docs/api/java/nio/charset/CharsetEncoder.html#unmappableCharacterAction())