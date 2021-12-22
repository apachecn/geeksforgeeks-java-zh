# 字符集包含 Java 中的()方法，示例

> 原文:[https://www . geesforgeks . org/charset-contains-method-in-Java-with-examples/](https://www.geeksforgeeks.org/charset-contains-method-in-java-with-examples/)

**contains()** 方法是 **java.nio.charset** 的内置方法，用于检查给定的字符集是否在另一个给定的字符集内。如果在 Y 中可表示的每个字符在 X 中也可表示，则字符集 X 包含字符集 Y。每个字符集都包含自身。然而，该方法计算包含关系的近似值。这意味着，如果给定的字符集在另一个字符集内，函数将返回 true。但是，如果它返回 false，那么给定的字符集不一定包含在这个字符集内。

**语法** :

```java
public abstract boolean contains(Charset second)
```

**参数**:该功能接受单个强制参数**秒**，指定要检查的字符集。

**返回值**:该函数返回一个布尔值。如果它包含给定的字符集，则返回 true，否则返回 false。

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
        Charset first = Charset.forName("ISO-2022-CN");

        // Second charset
        Charset second = Charset.forName("UTF-8");

        System.out.println(first.contains(second));
    }
}
```

**输出:**

```java
false

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
        Charset first = Charset.forName("UTF-16");

        // Second charset
        Charset second = Charset.forName("UTF-8");

        System.out.println(first.contains(second));
    }
}
```

**输出:**

```java
true

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/charset/charset . html # contains-Java . nio . charset . charset-](https://docs.oracle.com/javase/9/docs/api/java/nio/charset/Charset.html#contains-java.nio.charset.Charset-)