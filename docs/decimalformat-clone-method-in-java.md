# Java 中的 DecimalFormat clone()方法

> 原文:[https://www . geesforgeks . org/decimal format-clone-method-in-Java/](https://www.geeksforgeeks.org/decimalformat-clone-method-in-java/)

Java 中的 DecimalFormat 类的 clone()方法用于返回这个 DecimalFormat 实例的克隆。此方法重写 NumberFormat 类的 clone()方法。

**语法** :

```
Object clone()

```

**参数**:该方法不取任何参数。

**返回值**:该方法返回这个十进制格式实例的克隆。

下面的程序说明了克隆()方法的工作原理:

**程序 1** :

```
// Java program to illustrate the
// clone() method

import java.text.DecimalFormat;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create a DecimalFormat instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Set Currency
        deciFormat.setCurrency(Currency.getInstance(Locale.GERMANY));

        System.out.println(deciFormat.clone());
    }
}
```

**输出:**

```
java.text.DecimalFormat@674dc

```

**程序二** :

```
// Java program to illustrate the
// clone() method

import java.text.DecimalFormat;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create a DecimalFormat instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Set Currency
        deciFormat.getCurrencyInstance();

        System.out.println(deciFormat.clone());
    }
}
```

**输出:**

```
java.text.DecimalFormat@674dc

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/text/decimal format . html # clone()](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#clone())