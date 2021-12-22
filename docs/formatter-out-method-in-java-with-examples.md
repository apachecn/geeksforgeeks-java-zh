# Java 中的 Formatter out()方法，示例

> 原文:[https://www . geesforgeks . org/formatter-out-method-in-Java-with-examples/](https://www.geeksforgeeks.org/formatter-out-method-in-java-with-examples/)

**out()** 方法是 **java.util.Formatter** 的内置方法，它返回格式化程序输出的目的地。

**语法** :

```
public Appendable out()
```

**参数**:该功能不接受参数。

**返回值**:该函数返回输出的目的地。

**异常**:如果在函数调用之前格式化程序已经关闭，函数抛出**格式化程序关闭异常**。

下面是上述功能的实现:

**程序 1:**

```
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

        // Prints the destination of the output
        System.out.println("\nDestination: "
                           + frmt.out());
    }
}
```

**输出:**

```
What is your name? 
My name is Gopal Dave !

Destination: What is your name? 
My name is Gopal Dave !

```

**程序二:**

```
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

            // Prints the destination of the output
            System.out.println("\nDestination: "
                               + frmt.out());
        }
        catch (Exception e) {
            System.out.println("Exception is: "
                               + e);
        }
    }
}
```

**输出:**

```
What is your name? 
My name is Gopal Dave !
Exception is: java.util.FormatterClosedException

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/formatter . html # out()](https://docs.oracle.com/javase/10/docs/api/java/util/Formatter.html#out())