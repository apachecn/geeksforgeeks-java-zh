# Java 中的 decimal format setmaximumitegerdigits()方法

> 原文:[https://www . geeksforgeeks . org/decimal format-setmaximumintegergits-method-in-Java/](https://www.geeksforgeeks.org/decimalformat-setmaximumintegerdigits-method-in-java/)

**setmaximumitegerdigits()**方法是 java 中 **java.text.DecimalFomrat** 类的内置方法，用于设置一个数的整数部分所允许的最大位数。数字的整数部分是显示在小数点之前的部分。)符号。

**语法** :

```
public void setMaximumIntegerDigits(int newVal)

```

**参数**:该函数接受一个参数*新值*，这是该十进制格式实例允许设置的最大整数位数的新值。

**返回值**:函数不返回值。

下面是上述功能的实现:

**程序 1** :

```
// Java program to illustrate the
// setMaximumIntegerDigits() method

import java.text.DecimalFormat;
import java.text.DecimalFormatSymbols;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

        deciFormat.setMaximumIntegerDigits(6);

        System.out.println(deciFormat.format(12345678.3456789));
    }
}
```

**输出:**

```
345, 678.346

```

**程序二** :

```
// Java program to illustrate the
// setMaximumIntegerDigits() method

import java.text.DecimalFormat;
import java.text.DecimalFormatSymbols;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

        deciFormat.setMaximumIntegerDigits(6);

        System.out.println(deciFormat.format(1234.3456789));
    }
}
```

**输出:**

```
1, 234.346

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/text/decimal format . html # setmaximumintegergits(int)](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#setMaximumIntegerDigits(int))