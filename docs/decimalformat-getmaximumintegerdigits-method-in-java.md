# Java 中的 decimal format getmaximumitegerdigits()方法

> 原文:[https://www . geeksforgeeks . org/decimal format-getmaximumintegergits-method-in-Java/](https://www.geeksforgeeks.org/decimalformat-getmaximumintegerdigits-method-in-java/)

**getmaximumitegerdigits()**方法是 java 中 **java.text.DecimalFomrat** 类的内置方法，用于获取一个数字的整数部分所允许的最大位数。数字的整数部分被定义为小数点前的部分。).例如，在数字 123，45.678 中，整数部分是 123，45。

**语法** :

```
public int getMaximumIntegerDigits()

```

**参数**:该功能不接受任何参数。

**返回值**:该函数返回一个数的整数部分允许的最大位数。

下面是上述功能的实现:

**程序 1** :

```
// Java program to illustrate the
// getMaximumIntegerDigits() method

import java.text.DecimalFormat;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Print the Maximum Integral digits allowed
        System.out.println(deciFormat.getMaximumIntegerDigits());
    }
}
```

**输出:**

```
2147483647

```

**程序二** :

```
// Java program to illustrate the
// getMaximumIntegerDigits() method

import java.text.DecimalFormat;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();
        deciFormat.applyPattern("##.##");

        // Print the Maximum Integral digits allowed
        System.out.println(deciFormat.getMaximumIntegerDigits());
    }
}
```

**输出:**

```
2147483647

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/text/decimal format . html # getmaximumintegergits()](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#getMaximumIntegerDigits())