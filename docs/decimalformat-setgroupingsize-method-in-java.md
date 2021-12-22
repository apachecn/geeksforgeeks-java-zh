# Java 中的 DecimalFormat setGroupingSize()方法

> 原文:[https://www . geeksforgeeks . org/decimal format-setgroupingsize-method-in-Java/](https://www.geeksforgeeks.org/decimalformat-setgroupingsize-method-in-java/)

**setGroupingSize()** 方法是 java 中 **java.text.DecimalFomrat** 类的内置方法，用于设置这个 DecimalFormat 实例的分组大小。分组大小是十进制数的整数部分中每组的整数数量。例如，123，456.78 的分组大小是 3，12，34，56.78 的分组大小是 2。

**语法** :

```java
public void setGroupingSize(int newSize)

```

**参数**:该函数接受单个参数 *newSize* ，即需要设置的新整数组的大小。

**返回值**:函数不返回值。

下面是上述功能的实现:

**程序 1** :

```java
// Java program to illustrate the
// setGroupingSize() method

import java.text.DecimalFormat;
import java.text.DecimalFormatSymbols;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

        deciFormat.setGroupingSize(4);

        System.out.println(deciFormat.format(12345678.9));
    }
}
```

**输出:**

```java
1234, 5678.9

```

**程序二** :

```java
// Java program to illustrate the
// setGroupingSize() method

import java.text.DecimalFormat;
import java.text.DecimalFormatSymbols;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

        deciFormat.setGroupingSize(2);

        System.out.println(deciFormat.format(12345678.9));
    }
}
```

**输出:**

```java
12, 34, 56, 78.9

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/text/decimal format . html # setGroupingSize(int)](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#setGroupingSize(int))