# Java 中的格式化程序 ioException()方法，示例

> 原文:[https://www . geesforgeks . org/formatter-ioexception-method-in-Java-with-examples/](https://www.geeksforgeeks.org/formatter-ioexception-method-in-java-with-examples/)

**ioException()** 方法是 **java.util.Formatter** 的内置方法，它返回由该格式化程序的 Appendable 最后引发的 ioException。如果目的地的 *append()* 方法从不抛出 IOException，那么这个方法将总是返回 null。

**语法** :

```java
public IOException ioException()
```

**参数**:该功能不接受参数。

**返回值**:函数返回格式化程序的可追加的最后抛出的 IOException。

下面是上述功能的实现:

**程序 1:**

```java
// Java program to implement
// the above function

import java.util.Formatter;
import java.util.Locale;

public class Main {

    public static void main(String[] args)
    {

        // Get the string Buffer
        StringBuffer buffer
            = new StringBuffer();

        // Object creation
        Formatter frmt
            = new Formatter(buffer,
                            Locale.CANADA);

        // Format a new string
        String name = "My name is Gopal Dave";
        frmt.format("What is your name? \n%s !",
                    name);

        // Print the Formatted string
        System.out.println(frmt);

        // flushes the formatter
        frmt.flush();
        System.out.println("Flushed");
    }
}
```

**输出:**

```java
What is your name? 
My name is Gopal Dave !
Flushed

```

**程序二:**

```java
// Java program to implement
// the above function

import java.util.Formatter;
import java.util.Locale;

public class Main {

    public static void main(String[] args)
    {

        // Get the string Buffer
        StringBuffer buffer
            = new StringBuffer();

        // Object creation
        Formatter frmt
            = new Formatter(buffer,
                            Locale.CANADA);

        // Format a new string
        String name = "My name is Gopal Dave";
        frmt.format("What is your name? \n%s !",
                    name);

        System.out.println("The last exception thrown: "
                           + frmt.ioException());

        // Closes the format
        frmt.close();
    }
}
```

**输出:**

```java
The last exception thrown: null

```

**输出:**

```java
The last exception thrown: null

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/formatter . html # flush()](https://docs.oracle.com/javase/10/docs/api/java/util/Formatter.html#flush())