# Java 中的 DecimalFormat getCurrency()方法

> 原文:[https://www . geesforgeks . org/decimal format-getcurrency-method-in-Java/](https://www.geeksforgeeks.org/decimalformat-getcurrency-method-in-java/)

**getCurrency()** 方法是 java 中 **java.text.DecimalFomrat** 类的内置方法，用于返回在用该货币格式化货币值时使用的货币。如果没有要确定的有效货币，或者如果之前没有设置货币，则可以为空。

**语法** :

```
public Currency getCurrency()

```

**参数**:函数不接受单个参数。

**返回值**:该函数返回格式化货币值时使用的货币。

**错误和异常**:当数字格式类没有实现货币格式时，函数抛出 UnsupportedOperationException

下面是上述功能的实现:

**程序 1** :

```
// Java program to illustrate the
// getCurrency() method

import java.text.DecimalFormat;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Get the Currency Instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Stores the values
        String values = deciFormat.getCurrency()
                            .getDisplayName();

        // Prints the currency
        System.out.println(values);
    }
}
```

**输出:**

```
US Dollar

```

**程序二** :

```
// Java program to illustrate the
// getCurrency() method

import java.text.DecimalFormat;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Get the Currency Instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Sets the currency to Canadian Dollar
        deciFormat.setCurrency(
            Currency.getInstance(
                Locale.CANADA));

        // Stores the values
        String values = deciFormat.getCurrency()
                            .getDisplayName();

        // Prints the currency
        System.out.println(values);
    }
}
```

**输出:**

```
Canadian Dollar

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/text/decimal format . html # getCurrency()](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#getCurrency())