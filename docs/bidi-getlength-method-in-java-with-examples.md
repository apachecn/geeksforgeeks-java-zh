# Java 中的 Bidi getLength()方法，带示例

> 原文:[https://www . geesforgeks . org/bidi-get length-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bidi-getlength-method-in-java-with-examples/)

**java.text.Bidi** 类的 **getLength()** 方法用于获取此 Bidi 实例中文本的长度。

**语法:**

```java
public int getLength()
```

**参数**:这个方法不接受任何东西作为参数。

**返回值:**该方法将 bidi 文本的**长度**设为整数。

以下是说明 **getLength()** 方法的示例:

**例 1:**

```java
// Java program to demonstrate
// getLength() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing Bidi
        Bidi bidi
            = new Bidi("Geeks For Geeks", 0);

        // getting the length of line of text
        // using getLength() method
        int length = bidi.getLength();

        // display the result
        System.out.println("length of line : "
                           + length);
    }
}
```

**输出:**

```java
length of line : 15

```

**例 2:**

```java
// Java program to demonstrate
// getLength() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing Bidi
        Bidi bidi = new Bidi("Tajmahal", 0);

        // getting the length of line of text
        // using getLength() method
        int length = bidi.getLength();

        // display the result
        System.out.println("length of line : "
                           + length);
    }
}
```

**输出:**

```java
length of line : 8

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/bidi . html # getLength–](https://docs.oracle.com/javase/9/docs/api/java/text/Bidi.html#getLength--)