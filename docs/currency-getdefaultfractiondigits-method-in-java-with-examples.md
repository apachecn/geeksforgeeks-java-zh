# Java 中的 Currency getdefaultfractiondigts()方法示例

> 原文:[https://www . geeksforgeeks . org/currency-getdefaultfractionndigits-method-in-Java-with-examples/](https://www.geeksforgeeks.org/currency-getdefaultfractiondigits-method-in-java-with-examples/)

Java 中 **[币类](https://www.geeksforgeeks.org/java-util-currency-methods-example/)** 的**getDefaultFractionDigits()**方法用于检索或知道该币的小数位数，这是 ISO 4217 币码设置的默认值。

**语法:**

```java
public int getDefaultFractionDigits()
```

**参数:**此方法不接受任何参数。

**返回值:**此方法返回一个**整数值**，它是货币的默认小数位数。

**异常:**如果调用了无效代码，该方法将抛出**运行时错误**。

下面的程序说明了 getDefaultFractionDigits()方法的工作原理:

**程序 1:**

```java
// Java Code to illustrate
// getDefaultFractionDigits() method

import java.util.*;

public class Currency_Demo {
    public static void main(String[] args)
    {

        // Creating a currency with the code
        Currency curr_ency
            = Currency.getInstance("INR");

        // Getting the fraction digit of the currency
        int currency_fracdig
            = curr_ency.getDefaultFractionDigits();
        System.out.println("INR's fractions digits are: "
                           + currency_fracdig);
    }
}
```

**Output:**

```java
INR's fractions digits are: 2

```

**程序 2:**

```java
// Java Code to illustrate
// getDefaultFractionDigits() method

import java.util.*;

public class Currency_Demo {
    public static void main(String[] args)
    {

        // Creating a currency with the code
        Currency curr_ency
            = Currency.getInstance("JOD");

        // Getting the fraction digit of the currency
        int currency_fracdig
            = curr_ency.getDefaultFractionDigits();
        System.out.println("Jordan's fractions digits are: "
                           + currency_fracdig);
    }
}
```

**Output:**

```java
Jordan's fractions digits are: 3

```

**程序 3:** 为无效的货币代码。

```java
// Java Code to illustrate
// getDefaultFractionDigits() method

import java.util.*;

public class Currency_Demo {
    public static void main(String[] args)
    {

        try {
            // Creating a currency with the code
            Currency curr_ency
                = Currency.getInstance("JODA");

            // Getting the fraction digit of the currency
            int currency_fracdig
                = curr_ency.getDefaultFractionDigits();
            System.out.println("Jordan's fractions digits are: "
                               + currency_fracdig);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
java.lang.IllegalArgumentException

```