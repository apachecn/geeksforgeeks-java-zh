# Java 中的 decimal format getMinimumFractionDigits()方法

> 原文:[https://www . geesforgeks . org/decimal format-getminimumrocindigts-method-in-Java/](https://www.geeksforgeeks.org/decimalformat-getminimumfractiondigits-method-in-java/)

**getMinimumFractionDigits()**方法是 java 中 **java.text.DecimalFomrat** 类的内置方法，用于获取数字的小数或小数部分允许的最小位数。

**语法** :

```java
public int getMinimumFractionDigits()

```

**参数**:该功能不接受任何参数。

**返回值**:该函数返回一个数字的小数部分允许的最小位数。

下面是上述功能的实现:

**程序 1** :

```java
// Java program to illustrate the
// getMinimumFractionDigits() method

import java.text.DecimalFormat;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Print the Minimum fraction digits allowed
        System.out.println(deciFormat.getMinimumFractionDigits());
    }
}
```

**输出:**

```java
0

```

**程序二** :

```java
// Java program to illustrate the
// getMinimumFractionDigits() method

import java.text.DecimalFormat;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();
        deciFormat.applyPattern("##.##");

        // Print the minimum fractional digits allowed
        System.out.println(deciFormat.getMinimumFractionDigits());
    }
}
```

**输出:**

```java
0

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/text/decimal format . html # getMinimumFractionDigits()](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#getMinimumFractionDigits())