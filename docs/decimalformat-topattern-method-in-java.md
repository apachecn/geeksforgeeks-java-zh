# Java 中的十进制格式 toPattern()方法

> 原文:[https://www . geesforgeks . org/decimal format-topattern-method-in-Java/](https://www.geeksforgeeks.org/decimalformat-topattern-method-in-java/)

Java 中**十进制格式**类的 **toPattern()** 方法用于将该十进制格式的当前模式的格式转换为字符串格式。这个转换后的字符串表示用于格式化这个十进制格式实例的当前状态的模式。

**语法** :

```
public String toPattern()

```

**参数**:该方法不接受任何参数。

**返回值:**该方法返回一个字符串，该字符串表示用于格式化该十进制格式实例的当前状态的模式。

下面的程序说明了上述方法:

**程序 1** :

```
// Java program to illustrate the
// toPattern() method

import java.text.DecimalFormat;

public class GFG {

    public static void main(String[] args)
    {

        // Create a DecimalFormat instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Convert the current formatting state
        // to a string object
        String pattern = deciFormat.toPattern();

        System.out.println(pattern);
    }
}
```

**输出:**

```
#, ##0.###

```

**程序二** :

```
// Java program to illustrate the
// toPattern() method

import java.text.DecimalFormat;

public class GFG {

    public static void main(String[] args)
    {

        // Create a DecimalFormat instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Apply a new pattern
        deciFormat.applyPattern("##, ##.##");

        // Convert the current formatting state
        // to a string object
        String pattern = deciFormat.toPattern();

        System.out.println(pattern);
    }
}
```

**输出:**

```
#, #0.## ;#, #0.##

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/text/decimal format . html # toPattern()](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#toPattern())