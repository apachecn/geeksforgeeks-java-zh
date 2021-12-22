# Java 中的 decimal format set decimal separatorwayshow()方法

> 原文:[https://www . geesforgeks . org/decimal format-setdecimal separatorwayshow-in-Java 方法/](https://www.geeksforgeeks.org/decimalformat-setdecimalseparatoralwaysshown-method-in-java/)

**setdecimalseparatolarwayshown()**方法是 java 中 **java.text.DecimalFomrat** 类的内置方法，用于设置是否为此十进制格式实例设置十进制符号分隔符。如果此方法设置为 true，那么对于整数值，十进制格式实例也将打印十进制分隔符(。).

例如，如果该方法为真，则 1234 将被打印为“ **1234。**”。

**语法** :

```
public void setDecimalSeparatorAlwaysShown(boolean val)

```

**参数**:该函数接受布尔类型的单个参数*值*。

**返回值**:函数不返回值。

下面是上述功能的实现:

**程序 1** :

```
// Java program to illustrate the
// setDecimalSeparatorAlwaysShown() method

import java.text.DecimalFormat;
import java.text.DecimalFormatSymbols;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

        deciFormat.setDecimalSeparatorAlwaysShown(true);

        System.out.println(deciFormat.format(12345));
    }
}
```

**输出:**

```
12, 345.

```

**程序二** :

```
// Java program to illustrate the
// setDecimalSeparatorAlwaysShown() method

import java.text.DecimalFormat;
import java.text.DecimalFormatSymbols;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

        deciFormat.setDecimalSeparatorAlwaysShown(false);

        System.out.println(deciFormat.format(12345));
    }
}
```

**输出:**

```
12, 345

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/text/decimal format . html # setdecimal separatorwayshow(布尔值)](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#setDecimalSeparatorAlwaysShown(boolean))