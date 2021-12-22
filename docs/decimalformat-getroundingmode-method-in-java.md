# Java 中的 DecimalFormat getRoundingMode()方法

> 原文:[https://www . geesforgeks . org/decimal format-getroundingmode-method-in-Java/](https://www.geeksforgeeks.org/decimalformat-getroundingmode-method-in-java/)

**getRoundingMode()** 方法是 java 中 **java.text.DecimalFomrat** 类的内置方法，用于获取舍入模式，该模式用于对这个 DecimalFormat 实例中的数字进行舍入。

**语法** :

```
public RoundingMode getRoundingMode()

```

**参数**:该功能不接受任何参数。

**返回值**:该函数返回此十进制格式实例用于舍入数字的舍入模式。

下面是上述功能的实现:

**程序 1** :

```
// Java program to illustrate the
// getRoundingMode() method

import java.text.DecimalFormat;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Print the rounding mode value
        System.out.println(deciFormat.getRoundingMode().name());
    }
}
```

**输出:**

```
HALF_EVEN

```

**程序二** :

```
// Java program to illustrate the
// getRoundingMode() method

import java.text.DecimalFormat;
import java.util.Currency;
import java.util.Locale;
import java.math.RoundingMode;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();
        deciFormat.setRoundingMode(RoundingMode.HALF_UP);

        // Print the Rounding Mode
        System.out.println(deciFormat.getRoundingMode());
    }
}
```

**输出:**

```
HALF_UP

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/text/decimal format . html # getRoundingMode()](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#getRoundingMode())