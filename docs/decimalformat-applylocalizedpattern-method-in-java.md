# Java 中的 decimal format applylocalized pattern()方法

> 原文:[https://www . geeksforgeeks . org/decimal format-applylocalized pattern-in-method-in-Java/](https://www.geeksforgeeks.org/decimalformat-applylocalizedpattern-method-in-java/)

Java 中 DecimalFormat 类的 applyLocalizedPattern()方法用于将本地化的字符串模式应用于这种 Decimal 格式。这个模式可以由用户设置。

**语法** :

```
public void applyLocalizedPattern(String pattern)

```

**参数**:该方法采用一个字符串类型的参数模式，并引用将用于格式化十进制模式的模式。

**返回值**:该方法返回 void 类型。

下面的程序说明了 applyLocalizedPattern()方法的工作原理:

**程序 1** :

```
// Java program to illustrate the
// applyLocalizedPattern method

import java.text.DecimalFormat;

public class Main {
    public static void main(String[] args)
    {

        DecimalFormat deciFormat = new DecimalFormat();

        deciFormat.applyLocalizedPattern("##, ##");
        System.out.println(deciFormat.format(-123456789.54321));
    }
}
```

**输出:**

```
-1, 23, 45, 67, 90

```

**程序二** :

```
// Java program to illustrate the
// applyLocalizedPattern method

import java.text.DecimalFormat;

public class Main {
    public static void main(String[] args)
    {

        DecimalFormat deciFormat = new DecimalFormat();

        deciFormat.applyLocalizedPattern("#, #00.0#");
        System.out.println(deciFormat.format(-123456789.54321));
    }
}
```

**输出:**

```
-123, 456, 789.54

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/text/decimal format . html # applylocalizeddature(Java . lang . string)](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#applyLocalizedPattern(java.lang.String))