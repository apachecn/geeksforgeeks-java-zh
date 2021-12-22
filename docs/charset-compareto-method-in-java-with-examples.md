# Java 中的 Charset compareTo()方法，带示例

> 原文:[https://www . geeksforgeeks . org/charset-compare to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/charset-compareto-method-in-java-with-examples/)

**compareTo()** 方法是 **java.nio.charset** 相互比较两个字符集的内置方法。通过它们的规范名称进行比较，不考虑大小写。

**语法** :

```java
public final int compareTo?(Charset second)
```

**参数**:该函数接受单个强制参数**第二个**，指定要比较的字符集。

**返回值**:该函数在比较两个偏移量后，返回一个可以是负、正或零的整数值。

下面是上述功能的实现:

**程序 1:**

```java
// Java program to demonstrate
// the above function

import java.nio.charset.Charset;
import java.util.Iterator;
import java.util.Map;

public class GFG {

    public static void main(String[] args)
    {

        // First charset
        Charset first = Charset.forName("UTF16");

        // Second charset
        Charset second = Charset.forName("UTF-8");

        // Compares and print
        System.out.println(first.compareTo(second));
    }
}
```

**输出:**

```java
-7

```

**程序二:**

```java
// Java program to demonstrate
// the above function
import java.nio.charset.Charset;
import java.util.Iterator;
import java.util.Map;

public class GFG {

    public static void main(String[] args)
    {

        // First charset
        Charset first = Charset.forName("ISO-2022-CN");

        // Second charset
        Charset second = Charset.forName("ISO-2022-CN");
        System.out.println(first.compareTo(second));
    }
}
```

**输出:**

```java
0

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/charset/charset . html # compare to-Java . nio . charset . charset-](https://docs.oracle.com/javase/9/docs/api/java/nio/charset/Charset.html#compareTo-java.nio.charset.Charset-)