# Java 中的 Charset hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/charset-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/charset-hashcode-method-in-java-with-examples/)

**hashCode()** 方法是 **java.nio.charset** 的内置方法，返回任何给定字符集的计算 hashCode。

**语法** :

```
public final int hashCode()
```

**参数**:该功能不接受任何参数。

**返回值**:该函数返回字符集的计算哈希值。

下面是上述功能的实现:

**程序 1:**

```
// Java program to demonstrate
// the above function
import java.nio.charset.Charset;
import java.util.Iterator;
import java.util.Map;

public class GFG {

    public static void main(String[] args)
    {

        // Gets the charset
        Charset first = Charset.forName("ISO-2022-CN");

        // Prints the hash-code
        System.out.println("The hash code for ISO-2022-CN is " + first.hashCode());
    }
}
```

**输出:**

```
The hash code for ISO-2022-CN is 1450311218

```

**程序二:**

```
// Java program to demonstrate
// the above function
import java.nio.charset.Charset;
import java.util.Iterator;
import java.util.Map;

public class GFG {

    public static void main(String[] args)
    {

        // Gets the charset
        Charset first = Charset.forName("x-windows-949");

        // Prints the hash-code
        System.out.println("The hash code for x-windows-949 is " + first.hashCode());
    }
}
```

**输出:**

```
The hash code for x-windows-949 is -1698752417

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/nio/charset/charset . html # hashCode()](https://docs.oracle.com/javase/10/docs/api/java/nio/charset/Charset.html#hashCode())