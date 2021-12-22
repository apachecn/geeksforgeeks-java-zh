# Java 中的 DecimalFormat getMultiplier()方法

> 原文:[https://www . geesforgeks . org/decimal format-get multiplier-in-method-Java/](https://www.geeksforgeeks.org/decimalformat-getmultiplier-method-in-java/)

方法是 java 中 **java.text.DecimalFomrat** 类的内置方法，用于获取以不同格式使用的乘数，如百分比、百分位数等。

**语法** :

```
public int getMultiplier()

```

**参数**:该功能不接受任何参数。

**返回值**:该函数返回不同格式使用的乘数值。

下面是上述功能的实现:

**程序 1** :

```
// Java program to illustrate the
// getMultiplier() method

import java.text.DecimalFormat;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Print the multiplier value
        System.out.println(deciFormat.getMultiplier());
    }
}
```

**输出:**

```
1

```

**程序二** :

```
// Java program to illustrate the
// getMultiplier() method

import java.text.DecimalFormat;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();
        deciFormat.getPercentInstance();

        // Print the multiplier value
        System.out.println(deciFormat.getMultiplier());
    }
}
```

**输出:**

```
1

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/text/decimal format . html # getMultiplier()](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#getMultiplier())