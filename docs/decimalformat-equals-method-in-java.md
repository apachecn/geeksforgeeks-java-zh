# Java 中的十进制格式等于()方法

> 原文:[https://www . geesforgeks . org/decimal format-equals-method-in-Java/](https://www.geeksforgeeks.org/decimalformat-equals-method-in-java/)

equals()方法是 **java.text.DecimalFormat** 类的内置方法，它接受一个作为对象的参数，如果这个参数对象与对象相同，则返回 true，否则返回 false。

**语法** :

```
public boolean equals(Object arg)

```

**参数**:该函数接受单个强制参数*参数*，该参数指定要比较的对象。

**返回值**:该函数返回一个布尔值。如果两个对象相同，则返回 true，否则返回 false。

下面是上述功能的实现:

**程序 1** :

```
// Java program to illustrate the
// equals() method

import java.text.DecimalFormat;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Get the Currency Instance
        DecimalFormat dF1 = new DecimalFormat();
        dF1.getCurrencyInstance();

        // Get the Currency Instance
        DecimalFormat dF2 = new DecimalFormat();
        dF2.getCurrencyInstance();

        // Check if equal or not
        if (dF1.equals(dF2))
            System.out.println("Yes both are equal");
        else
            System.out.println("Yes both are not equal");
    }
}
```

**输出:**

```
Yes both are equal

```

**程序二** :

```
// Java program to illustrate the
// equals() method

import java.text.DecimalFormat;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Get the Currency Instance
        DecimalFormat dF1 = new DecimalFormat();
        dF1.getCurrencyInstance();

        // Get Instance
        DecimalFormat dF2 = new DecimalFormat();
        dF2.setCurrency(Currency.getInstance(Locale.GERMANY));

        // Check if equal or not
        if (dF1.equals(dF2))
            System.out.println("Yes both are equal");
        else
            System.out.println("Yes both are not equal");
    }
}
```

**输出:**

```
Yes both are not equal

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/text/decimal format . html # clone()](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#clone())