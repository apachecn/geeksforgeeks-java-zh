# Java 中的闭包示例

> 原文:[https://www . geesforgeks . org/closes-in-Java-with-examples/](https://www.geeksforgeeks.org/closures-in-java-with-examples/)

一个[方法](https://www.geeksforgeeks.org/methods-in-java/)是执行一些特定任务并将结果返回给调用者的语句的集合。一个方法可以执行一些特定的任务而不返回任何东西。方法允许我们在不重新键入代码的情况下重用代码。在 Java 中，每个方法都必须是某个类的一部分，这个类不同于像 C、C++和 Python 这样的语言。在本文中，我们将了解一种名为闭包的函数。
在进入闭包之前，让我们先了解一下什么是 lambda 表达式。一个[λ表达式](https://www.geeksforgeeks.org/lambda-expressions-java-8/)基本上表达了功能[接口](https://www.geeksforgeeks.org/interfaces-in-java/)的实例(一个具有单一抽象方法的接口称为功能接口)。一个例子是 [java.lang.Runnable](https://www.geeksforgeeks.org/runnable-interface-in-java/) 。Lambda 表达式只实现抽象函数，因此实现函数接口。Lambda 表达式是在 Java 8 中添加的，并提供以下功能:

1.  允许将功能视为方法参数，或将代码视为数据。
2.  一种可以不属于任何类而创建的函数。
3.  lambda 表达式可以像对象一样传递，并按需执行。

lambda 表达式的主要限制是 lambda 表达式的作用域只是最终的。也就是说，我们不能改变 lambda 表达式中变量的值。假设我们定义了一个 lambda 表达式，其中我们增加了一个变量的值，它只是抛出了一个错误。为了解决这个错误，已经定义了闭包。
**闭包是内联函数值表达式，这意味着它们是具有有界变量的类函数。闭包可以作为参数传递给另一个函数。闭包让我们可以从内部函数访问外部函数。但是从 Java 1.6 开始，Java 不依赖闭包或者 Java 没有闭包。此外，匿名内部类在 Java 中不是闭包。使用闭包有助于数据隐私和 curry(curry 意味着将一个带有许多参数的函数分解为一个参数中的多个函数)。虽然闭包的概念在 [Javascript](https://www.geeksforgeeks.org/javascript-tutorial/) 中有更好的定义，但是闭包仍然可以使用 lambda 表达式来实现。实现闭包的语法是:** 

```java
(argument_list) -> {func_body}
```

**现在，让我们通过例子来理解如何实现闭包:** 

*   ****示例 1:** 在本例中，我们将首先实现一个不带参数或自变量的 lambda 表达式。** 

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to demonstrate
// how a closure is implemented
// using lambda expressions

import java.io.*;

// Defining an interface whose
// implementation is given in
// the lambda expression.
// This uses the concept of
// closures
interface SalutationInterface {
    public String salHello();
}

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Lambda Expression
        SalutationInterface obj = () ->
        {
            return "Hello, GFGians!";
        };

        // Calling the above interface
        System.out.println(obj.salHello());
    }
}
```

****Output:** 

```java
Hello, GFGians!
```** 

*   ****示例 2:** 在本例中，我们将了解如何实现采用多个参数的 lambda 表达式。** 

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to demonstrate
// how a closure is implemented
// using lambda expressions
import java.io.*;

// Defining an interface whose
// implementation is given in
// the lambda expression.
// This uses the concept of
// closures
interface concatStrings {
    public String concat(String a,
                         String b);
}

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Lambda Expression
        concatStrings s = (s1, s2)
            -> s1 + s2;

        System.out.println(
            s.concat("Hello, ",
                     "GFGians!"));
    }
}
```

****Output:** 

```java
Hello, GFGians!
```** 

*   ****例 3:** 在本例中，我们将使用一个自定义的功能界面，从提供的数字中显示月份。** 

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to demonstrate
// how a closure is implemented
// using lambda expressions

import java.io.*;

// Defining an interface whose
// implementation is given in
// the lambda expression.
// This uses the concept of
// closures
interface NumToMonth {
    public String convertToMonth(int x);
}

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Lambda Expression

        NumToMonth obj = new NumToMonth() {
            String[] months = { "Jan", "Feb", "Mar",
                                "Apr", "May", "Jun",
                                "Jul", "Aug", "Sep",
                                "Oct", "Nov", "Dec" };

            public String convertToMonth(int n)
            {
                return (n > 0 && n <= months.length)
                    ? months[n - 1]
                    : null;
            };
        };
        System.out.println(obj.convertToMonth(8));
    }
}
```

****Output:** 

```java
Aug
```**