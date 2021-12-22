# Java 中的 decimal format getmaximumfactiondigits()方法

> 原文:[https://www . geesforgeks . org/decimal format-getmaximumfactiondigits-method-in-Java/](https://www.geeksforgeeks.org/decimalformat-getmaximumfractiondigits-method-in-java/)

**getmaximumfactiondigits()**方法是 java 中的 **java.text.DecimalFomrat** 类的内置方法，用于获取一个数字的小数或小数部分所允许的最大位数。

**语法** :

```
public int getMaximumFractionDigits()

```

**参数**:该功能不接受任何参数。

**返回值**:该函数返回一个数字的小数部分允许的最大位数。

下面是上述功能的实现:

**程序 1** :

```
// Java program to illustrate the
// getMaximumFractionDigits() method

import java.text.DecimalFormat;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Print the Grouping Size
        System.out.println(deciFormat.getMaximumFractionDigits());
    }
}
```

**输出:**

```
3

```

**程序二** :

```
// Java program to illustrate the
// getMaximumFractionDigits() method

import java.text.DecimalFormat;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();
        deciFormat.applyPattern("##.##");

        // Print the Grouping Size
        System.out.println(deciFormat.getMaximumFractionDigits());
    }
}
```

**输出:**

```
2

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/text/decimal format . html # getmaximumfactiondigits()](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#getMaximumFractionDigits())