# Java 中的 DecimalFormat setCurrency()方法

> 原文:[https://www . geesforgeks . org/decimal format-set currency-method-in-Java/](https://www.geeksforgeeks.org/decimalformat-setcurrency-method-in-java/)

**setCurrency()** 方法是 java 中**Java . text . decimal FORMAT**类的内置方法，用于为这个将用于格式化数字的 DecimalFormat 实例设置 Currency。

**语法** :

```java
public void setCurrency(Currency currency)

```

**参数**:该函数接受单个参数*货币*，该货币是用于格式化数字的货币。

**返回值**:函数不返回值。

下面是上述功能的实现:

**程序 1** :

```java
// Java program to illustrate the
// setCurrency() method

import java.text.DecimalFormat;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Set the Currency
        deciFormat.setCurrency(Currency.getInstance(Locale.GERMANY));

        // Print the current Currency value
        System.out.println(deciFormat.getCurrency());
    }
}
```

**输出:**

```java
EUR

```

**程序二** :

```java
// Java program to illustrate the
// setCurrency() method

import java.text.DecimalFormat;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Set the Currency
        deciFormat.setCurrency(Currency.getInstance(Locale.CANADA));

        // Print the current Currency value
        System.out.println(deciFormat.getCurrency());
    }
}
```

**输出:**

```java
CAD

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/text/decimal format . html # setCurrency(Java . util . currency)](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#setCurrency(java.util.Currency))