# Java 中的 Currency getCurrencyCode()方法，带示例

> 原文:[https://www . geesforgeks . org/currency-getcurrency code-method-in-Java-with-examples/](https://www.geeksforgeeks.org/currency-getcurrencycode-method-in-java-with-examples/)

Java 中的 Currency code()Currency 类的 **getCurrencyCode()** 方法用于检索该货币的货币代码，实际上是 ISO 4217 官方的货币代码。

**语法:**

```java
CURRENCY.getCurrencyCode()
```

**参数:**此方法不接受任何参数。

**返回值:**此方法返回货币的 ISO 4217 货币代码。

**异常:**如果调用了无效代码，该方法将抛出*运行时错误*。

下面的程序说明了 getCurrencyCode()方法的工作原理:

**程序 1:**

```java
// Java Code to illustrate
// getCurrencyCode() method

import java.util.*;

public class Currency_Demo {
    public static void main(String[] args)
    {

        // Creating a currency with the code
        Currency curr_ency
            = Currency.getInstance("INR");

        // Getting the currency code
        String currency_code
            = curr_ency.getCurrencyCode();
        System.out.println("Currency Code of India is: "
                           + currency_code);
    }
}
```

**Output:**

```java
Currency Code of India is: INR

```

**程序 2:**

```java
// Java Code to illustrate
// getCurrencyCode() method

import java.util.*;

public class Currency_Demo {
    public static void main(String[] args)
    {

        // Creating a currency with the code
        Currency curr_ency
            = Currency.getInstance("USD");

        // Getting the currency code
        String currency_code
            = curr_ency.getCurrencyCode();
        System.out.println("Currency Code of USA is: "
                           + currency_code);
    }
}
```

**Output:**

```java
Currency Code of USA is: USD

```

**程序 3:** 为无效的货币代码。

```java
// Java Code to illustrate getCurrencyCode() method

import java.util.*;

public class Currency_Demo {
    public static void main(String[] args)
    {
        try {

            // Creating a currency with the code
            Currency curr_ency
                = Currency.getInstance("USDA");

            // Getting the currency code
            String currency_code
                = curr_ency.getCurrencyCode();
            System.out.println("Invalid Currency Code: "
                               + currency_code);
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