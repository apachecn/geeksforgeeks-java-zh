# Java 中的 decimal format setmaximumfactiondigits()方法

> 原文:[https://www . geesforgeks . org/decimal format-setmaximumfactiondigits-method-in-Java/](https://www.geeksforgeeks.org/decimalformat-setmaximumfractiondigits-method-in-java/)

**setmaximumfactiondigits()**方法是 java 中 **java.text.DecimalFomrat** 类的内置方法，用于设置数字小数部分允许的最大位数。数字的小数部分是显示在小数点后的部分。)符号。

**语法** :

```
public void setMaximumFractionDigits(int newVal)

```

**参数**:该函数接受一个参数*新值*，这是该十进制格式实例允许设置的最大小数位数的新值。

**返回值**:函数不返回值。

下面是上述功能的实现:

**程序 1** :

```
// Java program to illustrate the
// setMaximumFractionDigits() method

import java.text.DecimalFormat;
import java.text.DecimalFormatSymbols;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

        deciFormat.setMaximumFractionDigits(6);

        System.out.println(deciFormat.format(12.3456789));
    }
}
```

**输出:**

```
12.345679

```

**程序二** :

```
// Java program to illustrate the
// setMaximumFractionDigits() method

import java.text.DecimalFormat;
import java.text.DecimalFormatSymbols;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

        deciFormat.setMaximumFractionDigits(1);

        System.out.println(deciFormat.format(12.3456789));
    }
}
```

**输出:**

```
12.3

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/text/decimal format . html # setmaximumfactiondigits(int)](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#setMaximumFractionDigits(int))