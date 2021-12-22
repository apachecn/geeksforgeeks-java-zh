# Java 中的 DecimalFormat getGroupingSize()方法

> 原文:[https://www . geesforgeks . org/decimal format-getgroupingsize-method-in-Java/](https://www.geeksforgeeks.org/decimalformat-getgroupingsize-method-in-java/)

**getGroupingSize()** 方法是 java 中**Java . text . DecimalFormat**类的内置方法，用于获取这个 decimal format 实例的分组大小。分组大小定义为数字整数部分中分组分隔符之间的位数。例如，在数字“123，456.78”中，分组大小为 3

**语法** :

```java
public int getGroupingSize()

```

**参数**:该功能不接受任何参数。

**返回值**:该函数将该十进制格式实例的分组大小作为整数值返回。

下面是上述功能的实现:

**程序 1** :

```java
// Java program to illustrate the
// getGroupingSize() method

import java.text.DecimalFormat;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Print the Grouping Size
        System.out.println(deciFormat.getGroupingSize());
    }
}
```

**输出:**

```java
3

```

**程序二** :

```java
// Java program to illustrate the
// getGroupingSize() method

import java.text.DecimalFormat;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();
        deciFormat.applyPattern("##, ##");

        // Print the Grouping Size
        System.out.println(deciFormat.getGroupingSize());
    }
}
```

**输出:**

```java
2

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/text/decimal format . html # getGroupingSize()](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#getGroupingSize())