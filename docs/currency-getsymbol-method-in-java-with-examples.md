# Java 中的货币获取符号方法，示例

> 原文:[https://www . geesforgeks . org/currency-getsymbol-method-in-Java-with-examples/](https://www.geeksforgeeks.org/currency-getsymbol-method-in-java-with-examples/)

Java 中 Currency 类的 **getSymbol()** 方法用于检索货币代码的官方符号。

**语法:**

```java
CURRENCY.getSymbol()
```

**参数:**此方法不接受任何参数。

**返回值:**此方法返回货币的官方符号。

**异常:**如果调用了无效代码，该方法将抛出*运行时错误*。

下面的程序说明了 getSymbol()方法的工作原理:

**程序 1:**

```java
// Java Code to illustrate getSymbol() method

import java.util.*;

public class Currency_Demo {
    public static void main(String[] args)
    {

        // Creating a currency with the code
        Currency curr_ency
            = Currency.getInstance("INR");

        // Getting the symbol of the currency
        String currency_symbol
            = curr_ency.getSymbol();
        System.out.println("Symbol for the currency of India is: "
                           + currency_symbol);
    }
}
```

**Output:**

```java
Symbol for the currency of India is: INR

```

**程序 2:**

```java
// Java Code to illustrate getSymbol() method

import java.util.*;

public class Currency_Demo {
    public static void main(String[] args)
    {

        // Creating a currency with the code
        Currency curr_ency
            = Currency.getInstance("USD");

        // Getting the symbol of the currency
        String currency_symbol
            = curr_ency.getSymbol();
        System.out.println("Symbol for the currency of USA is: "
                           + currency_symbol);
    }
}
```

**Output:**

```java
Symbol for the currency of USA is: $

```

**程序 3:** 为无效的货币代码。

```java
// Java Code to illustrate getSymbol() method

import java.util.*;

public class Currency_Demo {
    public static void main(String[] args)
    {
        try {

            // Creating a currency with the code
            Currency curr_ency
                = Currency.getInstance("USDA");

            // Getting the symbol of the currency
            String currency_symbol
                = curr_ency.getSymbol();
            System.out.println("Symbol for the currency of USA is: "
                               + currency_symbol);
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