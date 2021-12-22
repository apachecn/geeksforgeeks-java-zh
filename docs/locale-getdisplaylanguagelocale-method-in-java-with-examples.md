# Java 中的 Locale getDisplayLanguage(Locale)方法，示例

> 原文:[https://www . geesforgeks . org/locale-getdisplaylanguagelocale-method-in-Java-with-examples/](https://www.geeksforgeeks.org/locale-getdisplaylanguagelocale-method-in-java-with-examples/)

Java 中 **[语言环境类](https://www.geeksforgeeks.org/java-util-locale-class-java-set-1/)** 的**getDisplayLanguage(Locale inLoc)**方法用于获取指定语言环境的语言名称。如果有可能，返回的名称将根据 inLocale 进行本地化。

**语法:**

```java
public String getDisplayLanguage(Locale inLoc)
```

**参数:**该方法取 Locale 类型的一个参数 *inLoc* ，指名称的本地化显示。

**返回值:**这个方法返回适合给定区域设置的显示语言的名称。

**异常:**如果参数 inLoc 为空，则方法抛出 **[空指针异常](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)** 。

以下程序说明了 getDisplayLanguage()方法的工作:
**程序 1:**

```java
// Java code to illustrate getDisplayLanguage() method

import java.util.*;

public class Locale_Demo {
    public static void main(String[] args)
    {

        // Creating a new locale
        Locale first_locale
            = new Locale("en", "US");

        // Displaying first locale
        System.out.println("First Locale: "
                           + first_locale);

        // Displaying the language of this locale
        System.out.println("Language: "
                           + first_locale
                                 .getDisplayLanguage(
                                     new Locale("fr", "FR")));
    }
}
```

**Output:**

```java
First Locale: en_US
Language: anglais

```

**程序 2:**

```java
// Java code to illustrate getDisplayLanguage() method

import java.util.*;

public class Locale_Demo {
    public static void main(String[] args)
    {

        // Creating a new locale
        Locale first_locale
            = new Locale("en", "US");

        // Displaying first locale
        System.out.println("First Locale: "
                           + first_locale);

        // Displaying the language of this locale
        System.out.println("Language: "
                           + first_locale
                                 .getDisplayLanguage(
                                     new Locale("", "FR")));
    }
}
```

**Output:**

```java
First Locale: en_US
Language: English

```