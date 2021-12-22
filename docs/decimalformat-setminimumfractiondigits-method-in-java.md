# Java 中的 decimal format setMinimumFractionDigits()方法

> 原文:[https://www . geeksforgeeks . org/decimal format-set minimum fractiondigts-method-in-Java/](https://www.geeksforgeeks.org/decimalformat-setminimumfractiondigits-method-in-java/)

**setMinimumFractionDigits()**方法是 java 中 **java.text.DecimalFomrat** 类的内置方法，用于设置数字小数部分允许的最小位数。数字的小数部分是显示在小数点后的部分。)符号。

**语法** :

```java
public void setMinimumFractionDigits(int newVal)

```

**参数**:该函数接受一个参数*新值*，这是允许为此十进制格式实例设置的最小小数位数的新值。

**返回值**:函数不返回值。

下面是上述功能的实现:

**程序 1** :

```java
// Java program to illustrate the
// setMinimumFractionDigits() method

import java.text.DecimalFormat;
import java.text.DecimalFormatSymbols;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

        deciFormat.setMinimumFractionDigits(6);

        System.out.println(deciFormat.format(12.34));
    }
}
```

**输出:**

```java
12.340000

```

**程序二** :

```java
// Java program to illustrate the
// setMinimumFractionDigits() method

import java.text.DecimalFormat;
import java.text.DecimalFormatSymbols;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

        deciFormat.setMinimumFractionDigits(1);

        System.out.println(deciFormat.format(12.345));
    }
}
```

**输出:**

```java
12.345

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/text/decimal format . html # setMinimumFractionDigits(int)](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#setMinimumFractionDigits(int))