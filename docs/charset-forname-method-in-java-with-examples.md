# Java 中的 Charset forName()方法，带示例

> 原文:[https://www . geeksforgeeks . org/charset-for name-method-in-Java-with-examples/](https://www.geeksforgeeks.org/charset-forname-method-in-java-with-examples/)

**forName()** 方法是 **java.nio.charset** 的内置方法，为命名的 charset 返回一个 charset 对象。在这个函数中，我们传递一个规范名称或别名，并返回其各自的字符集名称。

**语法** :

```java
public static Charset forName?(String charsetName)
```

**参数**:该函数接受单个强制参数**字符集名称**，该参数指定要返回对象名称的规范名称或别名。

**返回值**:该函数为命名字符集返回一个字符集对象。

**错误和异常**:函数抛出三个异常如下所示:

*   *[illegalcharsetnameexception]* : Thrown if the given character set name is illegal.
*   *[illegalargumentexception]* : Thrown if the given character set name is empty.
*   *If not, throw* : If the named character set is not supported in this instance of Java virtual machine.

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

        // Gets the charset
        Charset first = Charset.forName("ISO-2022-CN");

        // Prints the object
        System.out.println("The name for ISO-2022-CN is " + first);
    }
}
```

**输出:**

```java
The name for ISO-2022-CN is ISO-2022-CN

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

        // Gets the charset
        Charset first = Charset.forName("UTF16");

        // Prints the object
        System.out.println("The name for UTF16 is " + first);
    }
}
```

**输出:**

```java
The name for UTF16 is UTF-16

```

**程序 3**

```java
// Java program to demonstrate
// the above function
import java.nio.charset.Charset;
import java.util.Iterator;
import java.util.Map;

public class GFG {

    public static void main(String[] args)
    {

        try {

            // Gets the charset
            Charset first = Charset.forName("");

            // Prints the object
            System.out.println("The name for null is " + first);
        }
        catch (Exception e) {

            // Prints the exception
            System.out.println("The exception is: " + e);
        }
    }
}
```

**输出:**

```java
The exception is: java.nio.charset.IllegalCharsetNameException:

```

**程序 4**

```java
// Java program to demonstrate
// the above function
import java.nio.charset.Charset;
import java.util.Iterator;
import java.util.Map;

public class GFG {

    public static void main(String[] args)
    {

        try {

            // Gets the charset
            Charset first = Charset.forName("gopal");

            // Prints the object
            System.out.println("The name for gopal is " + first);
        }
        catch (Exception e) {

            // Prints the exception
            System.out.println("The exception is: " + e);
        }
    }
}
```

**输出:**

```java
The exception is: java.nio.charset.UnsupportedCharsetException: gopal

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/nio/charset/charset . html # for name(Java . lang . string)](https://docs.oracle.com/javase/10/docs/api/java/nio/charset/Charset.html#forName(java.lang.String))