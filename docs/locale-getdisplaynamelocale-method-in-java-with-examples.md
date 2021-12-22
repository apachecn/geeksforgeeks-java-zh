# Java 中的 Locale getDisplayName(Locale)方法，示例

> 原文:[https://www . geesforgeks . org/locale-getdisplayname locale-method-in-Java-with-examples/](https://www.geeksforgeeks.org/locale-getdisplaynamelocale-method-in-java-with-examples/)

Java 中 **[Locale 类](https://www.geeksforgeeks.org/java-util-locale-class-java-set-1/)** 的**getDisplayName(Locale*inLoc*)**方法用于获取指定地区的完整名称，包括语言、国家或其他变体。这是根据用户的方便来显示的。

**语法:**

```java
public String getDisplayName(Locale *inLoc*)
```

**参数:**该方法取 Locale 类型的一个参数 *inLoc* ，指名称的本地化显示。

**返回值:**这个方法返回适合给定区域设置的显示语言的名称。

**异常:**如果参数 inLoc 为空，则方法抛出 **[空指针异常](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)** 。

以下程序说明了 getDisplayName()方法的工作方式:
**程序 1:**

```java
// Java code to illustrate getDisplayName() method

import java.util.*;

public class Locale_Demo {
    public static void main(String[] args)
    {

        // Creating a new locale
        Locale first_locale
            = new Locale("en", "In");

        // Displaying first locale
        System.out.println("First Locale: "
                           + first_locale);

        // Displaying the locale
        System.out.println("Language: "
                           + first_locale
                                 .getDisplayName(
                                     new Locale("fr", "French")));
    }
}
```

**Output:**

```java
First Locale: en_IN
Language: anglais (Inde)

```

**程序 2:**

```java
// Java code to illustrate getDisplayName() method

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

        // Displaying the locale
        System.out.println("Language: "
                           + first_locale
                                 .getDisplayName(
                                     new Locale("En", "In")));
    }
}
```

**Output:**

```java
First Locale: en_US
Language: English (United States)

```

**参考:**[https://docs . Oracle . com/javae/7/docs/API/Java/util/locale . html # getdisplayname(Java . util . locale)](https://docs.oracle.com/javase/7/docs/api/java/util/Locale.html#getDisplayName(java.util.Locale))