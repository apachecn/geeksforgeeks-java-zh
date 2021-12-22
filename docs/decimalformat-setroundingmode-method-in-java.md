# Java 中的 DecimalFormat setRoundingMode()方法

> 原文:[https://www . geesforgeks . org/decimal format-setroundingmode-method-in-Java/](https://www.geeksforgeeks.org/decimalformat-setroundingmode-method-in-java/)

**setRoundingMode()** 方法是 java 中 **java.text.DecimalFomrat** 类的内置方法，用于设置与此 DecimalFormat 实例一起使用的 RoundingMode，以舍入十进制数字。

**语法** :

```java
public void setRoundingMode(RoundingMode roundingMode)

```

**参数**:该函数接受单个参数*舍入模式*，这是为此十进制格式实例设置的舍入模式实例。

**返回值**:函数不返回值。

下面是上述功能的实现:

**程序 1** :

```java
// Java program to illustrate the
// setRoundingMode() method

import java.text.DecimalFormat;
import java.text.DecimalFormatSymbols;
import java.math.RoundingMode;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Set the rounding mode as CEILING
        deciFormat.setRoundingMode(RoundingMode.CEILING);

        System.out.println(deciFormat.format(1234.5555));
    }
}
```

**输出:**

```java
1, 234.556

```

**程序二** :

```java
// Java program to illustrate the
// setRoundingMode() method

import java.text.DecimalFormat;
import java.text.DecimalFormatSymbols;
import java.math.RoundingMode;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Set the rounding mode as HALF_DOWN
        deciFormat.setRoundingMode(RoundingMode.HALF_DOWN);

        System.out.println(deciFormat.format(1234.5555));
    }
}
```

**输出:**

```java
1, 234.555

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/text/decimal format . html # setRoundingMode(Java . math . roundingmode)](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#setRoundingMode(java.math.RoundingMode))