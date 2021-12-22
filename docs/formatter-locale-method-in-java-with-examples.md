# Java 中的格式化程序 locale()方法，示例

> 原文:[https://www . geesforgeks . org/formatter-locale-method-in-Java-with-examples/](https://www.geeksforgeeks.org/formatter-locale-method-in-java-with-examples/)

**locale()** 方法是 **java.util.Formatter** 的内置方法，它返回一个区域设置。该区域设置由格式化程序构造设置。具有区域设置参数的此对象的 format 方法不会更改此值。

**语法** :

```java
public Locale locale()
```

**参数**:该功能不接受参数。

**返回值**:如果没有应用本地化，函数返回空值，否则返回一个已经初始化为格式化程序的区域设置。

**异常**:如果在函数调用之前格式化程序已经关闭，函数抛出**格式化程序关闭异常**。

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

        // Prints the format that has been set
        // Initially to the formatter
        System.out.println("Locale: "
                           + frmt.locale());
    }
}
```

**输出:**

```java
What is your name? 
My name is Gopal Dave !
Locale: en_CA

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
        try {

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

            // Formatter closed
            frmt.close();

            // Prints the format that has been set
            // Initially to the formatter
            System.out.println("Locale: "
                               + frmt.locale());
        }
        catch (Exception e) {
            System.out.println("Exception is: "
                               + e);
        }
    }
}
```

**输出:**

```java
What is your name? 
My name is Gopal Dave !
Exception is: java.util.FormatterClosedException

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/formatter . html # locale()](https://docs.oracle.com/javase/10/docs/api/java/util/Formatter.html#locale())