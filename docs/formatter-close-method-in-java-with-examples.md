# Java 中的 Formatter close()方法，示例

> 原文:[https://www . geesforgeks . org/formatter-close-method-in-Java-with-examples/](https://www.geeksforgeeks.org/formatter-close-method-in-java-with-examples/)

**close()** 方法是关闭格式化程序的 **java.util.Formatter** 的内置方法。万一已经关了，就没效果了。关闭它意味着它将释放已经持有的资源。

**语法** :

```
public void close()
```

**参数**:该功能不接受参数。

**返回值**:函数不返回任何东西，只是关闭格式化程序。因此返回类型是无效的。

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
        StringBuffer buffer = new StringBuffer();

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

        // Prints the formatted string
        // again since it is not closed
        System.out.println(frmt);

        // close the frmt
        frmt.close();
    }
}
```

**输出:**

```
What is your name? 
My name is Gopal Dave !
What is your name? 
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

        // Get the string Buffer
        StringBuffer buffer
            = new StringBuffer();

        // Object creation
        Formatter frmt
            = new Formatter(buffer,
                            Locale.CANADA);

        // Format a new string
        String name = "Java programs are fun";
        frmt.format("%s !", name);

        System.out.println(frmt);

        // close the frmt
        frmt.close();
    }
}
```

**输出:**

```
Java programs are fun !

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/formatter . html # close()](https://docs.oracle.com/javase/10/docs/api/java/util/Formatter.html#close())