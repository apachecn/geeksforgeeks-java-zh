# Java 中的 Bidi getLevelAt()方法，带示例

> 原文:[https://www . geesforgeks . org/bidi-getlevelat-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bidi-getlevelat-method-in-java-with-examples/)

类的 **getLevelAt()** 方法用于提供出现在 Bidi 文本行上特定点的特定字符的解析级别。

**语法:**

```java
public int getLevelAt(int offset)
```

**参数**:该方法取需要解析级别的文本行中当前字符的偏移量。

**返回值:**如果偏移量小于零或大于 bidi 文本的整个长度，则该方法为特定字符提供解析级别，该字符的偏移量作为参数给出，而不仅仅返回等效的基本级别。

以下是说明 **getLevelAt()** 方法的示例:

**例 1:**

```java
// Java program to demonstrate
// getLevelAt() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing Bidi
        Bidi bidi = new Bidi("Geeks for Geeks", 0);

        int offset = 3;

        // getting resolved level of Character
        // using getLevelAt() method
        int status = bidi.getLevelAt(offset);

        // display the result
        if (offset > 0
            && (bidi.getLength()) > offset)
            System.out.println(
                "resolved level of the "
                + "Character at offset "
                + offset + " is "
                + status);
        else
            System.out.println(
                "base direction level is "
                + status);
    }
}
```

**输出:**

```java
resolved level of the Character at offset 3 is 0

```

**例 2:**

```java
// Java program to demonstrate
// getLevelAt() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing Bidi
        Bidi bidi = new Bidi("Tajmahal", 0);

        int offset = -3;

        // getting resolved level of Character
        // using getLevelAt() method
        int status = bidi.getLevelAt(offset);

        // display the result
        if (offset > 0
            && (bidi.getLength()) > offset)
            System.out.println(
                "resolved level of the "
                + "Character at offset "
                + offset + " is "
                + status);
        else
            System.out.println(
                "base direction level is "
                + status);
    }
}
```

**输出:**

```java
base direction level is 0

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/bidi . html # getLevelAt-int-](https://docs.oracle.com/javase/9/docs/api/java/text/Bidi.html#getLevelAt-int-)