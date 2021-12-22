# Java 中的 decimal format getminimumentegerdigits()方法

> 原文:[https://www . geesforgeks . org/decimal format-getminimumentegerdigits-method-in-Java/](https://www.geeksforgeeks.org/decimalformat-getminimumintegerdigits-method-in-java/)

**getminimumentegerdigits()**方法是 java 中 **java.text.DecimalFomrat** 类的内置方法，用于获取一个数字的整数部分所允许的最小位数。数字的整数部分被定义为小数点前的部分。).例如，在数字 123，45.678 中，整数部分是 123，45。

**语法** :

```java
public int getMinimumIntegerDigits()

```

**参数**:该功能不接受任何参数。

**返回值**:该函数返回一个数的整数部分允许的最小位数。

下面是上述功能的实现:

**程序 1** :

```java
// Java program to illustrate the
// getMinimumIntegerDigits() method

import java.text.DecimalFormat;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Print the minimum Integral digits allowed
        System.out.println(deciFormat.getMinimumIntegerDigits());
    }
}
```

**输出:**

```java
1

```

**程序二** :

```java
// Java program to illustrate the
// getMinimumIntegerDigits() method

import java.text.DecimalFormat;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();
        deciFormat.applyPattern("##.##");

        // Print the Minimum Integral digits allowed
        System.out.println(deciFormat.getMinimumIntegerDigits());
    }
}
```

**输出:**

```java
1

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/text/decimal format . html # getminimumentegerdigits()](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#getMinimumIntegerDigits())