# Java 中的国际化(I18N)

> 原文:[https://www . geesforgeks . org/国际化 18n-in-java/](https://www.geeksforgeeks.org/internationalizationi18n-in-java/)

**国际化(I18N)** 是设计 web 应用程序的过程，以这种方式自动为各种国家、各种语言和各种货币提供支持，而不在应用程序中执行任何更改，称为国际化(I18N)。它之所以被称为 I18N，是因为介于 I 和 N 之间；有 18 个字符；这就是 I18N 的原因。

如果您正在开发一个应用程序，并且想要显示消息、货币、日期、时间等，那么国际化是 java 强大的概念之一。，根据具体地区或语言。

**例:**我们都知道亚马逊网站。它在全世界都有。我们印度人也访问网站，任何其他国家的人也访问网站。如果任何请求来自印度人，那么亚马逊网站的响应应该是印度人可以理解的形式，比如货币应该是 INR 等。但与此同时，如果美国人访问该网站，那么该网站给出的响应/信息应该是美国人可以理解的某种形式，比如这里的货币应该是美元。上述过程被称为国际化(I18N)。

***我们可以使用以下三个类来实现国际化:***

*   本地
*   [NumberFormat](https://www.geeksforgeeks.org/numberformat-class-java/)
*   DateFormat(日期格式)

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate Program
// without Internationalization

public class InternationalizationDemo
{
    public static void main(String[] args)
    {
        System.out.println("Hello");
        System.out.println("Geeks");
        System.out.println("How are you?");
    }
}
```

**Output**

```java
Hello
Geeks
How are you?
```

**解释:**如果我们想让这个程序为生活在意大利和西班牙的人们显示同样的信息。不幸的是，我们的编程人员不是多语言的，然后我们必须在意大利和西班牙翻译上述信息。假设我们不知道意大利和西班牙的语言。那么我们的节目将不会为意大利和西班牙人民说话。看起来这个项目需要国际化。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate Program with
// Internationalization

import java.text.*;
import java.util.*;

class NumberFormatDemo {
    public static void main(String[] args)
    {
        // Here we get the below number
        // representation in various countries
        double d = 123456.789;
        NumberFormat nf
            = NumberFormat.getInstance(Locale.ITALY);
        NumberFormat nf1
            = NumberFormat.getInstance(Locale.US);
        NumberFormat nf2
            = NumberFormat.getInstance(Locale.CHINA);

        System.out.println("ITALY representation of " + d
                           + " : " + nf.format(d));

        System.out.println("US representation of " + d
                           + " : " + nf1.format(d));

        System.out.println("CHINA representation of " + d
                           + " : " + nf2.format(d));
    }
}
```

**Output**

```java
ITALY representation of 123456.789 : 123.456,789
US representation of 123456.789 : 123,456.789
CHINA representation of 123456.789 : 123,456.789
```