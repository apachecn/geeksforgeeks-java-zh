# Java 中的 Currency getInstance()方法，带示例

> 原文:[https://www . geesforgeks . org/currency-getinstance-method-in-Java-with-examples/](https://www.geeksforgeeks.org/currency-getinstance-method-in-java-with-examples/)

Java 中 Currency 类的 **getInstance()** 方法用于检索给定货币代码的该货币的实例。
**语法:**

```java
CURRENCY.getInstance(String currency_code)
```

**参数:**该方法接受一个参数*货币 _ 代码*，该参数是特定货币的货币。
**返回值:**此方法返回货币代码的货币实例。
**异常:**如果调用了无效代码，该方法将抛出*运行时错误*。
下面的程序说明了 getInstance()方法的工作:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Code to illustrate getInstance() method

import java.util.*;

public class Currency_Demo {
    public static void main(String[] args)
    {

        // Creating a currency with the code
        Currency curr_ency
            = Currency.getInstance("INR");

        // Getting the currency code
        System.out.println("Currency Code of India is: "
                           + curr_ency.toString());
    }
}
```

**Output:** 

```java
Currency Code of India is: INR
```

**节目 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Code to illustrate toString() method

import java.util.*;

public class Currency_Demo {
    public static void main(String[] args)
    {

        // Creating a currency with the code
        Currency curr_ency
            = Currency.getInstance("USD");

        // Getting the currency code
        System.out.println("Currency Code of USA is: "
                           + curr_ency.toString());
    }
}
```

**Output:** 

```java
Currency Code of USA is: USD
```

**程序 3:** 为无效的货币代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Code to illustrate getInstance() method

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
                = curr_ency.toString();
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