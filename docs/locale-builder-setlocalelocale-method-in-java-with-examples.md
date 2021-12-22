# 场所。Java 中的 Builder setLocale(Locale)方法，示例

> 原文:[https://www . geesforgeks . org/locale-builder-setlocallecale-method-in-Java-with-examples/](https://www.geeksforgeeks.org/locale-builder-setlocalelocale-method-in-java-with-examples/)

**[java.util](https://www.geeksforgeeks.org/java-util-package-java/) 的 **setLocale(Locale)** 方法。[场所。Java 中的 Builder 类](https://www.geeksforgeeks.org/tag/java-locale-builder/)** 用来重置这个 Locale。生成器转换为指定的区域设置。这意味着此方法将重置 Locale 的当前状态。生成器实例来匹配所提供的区域设置并返回它。

**语法:**

```java
public Locale.Builder setLocale(Locale locale)

```

**参数:**该方法接受**地区**作为参数，该参数是要设置到该地区的地区。生成器实例。

**返回值:**该方法返回一个**地区。构建器实例**，这是该场所的状态。生成器设置为指定的区域设置。

**异常:**此方法抛出以下异常:

*   IllformedLocaleException: If the specified locale has any improperly formatted fields.
*   NullPointerException: If the specified locale is set to null

**程序 1:**

```java
// Java program to demonstrate
// the above method

import java.util.*;
import java.util.Locale.*;

public class LocaleBuilderDemo {
    public static void main(String[] args)
    {

        // Creating a new Locale.Builder
        Locale.Builder localeBuilder
            = new Builder();

        // Displaying Locale.Builder
        System.out.println("LocaleBuilder: "
                           + localeBuilder);

        // setting the locale of Locale.Builder
        Locale locale = Locale.FRANCE;
        System.out.println("Setting the Locale: "
                           + locale);

        localeBuilder
            = localeBuilder.setLocale(locale);

        // Displaying Locale.Builder
        System.out.println("Updated LocaleBuilder: "
                           + localeBuilder);
    }
}
```

**输出:**

```java
LocaleBuilder: java.util.Locale$Builder@232204a1
Setting the Locale: fr_FR
Updated LocaleBuilder: java.util.Locale$Builder@232204a1

```

**程序二:**

```java
// Java program to demonstrate
// the above method

import java.util.*;
import java.util.Locale.*;

public class LocaleBuilderDemo {
    public static void main(String[] args)
    {

        // Creating a new Locale.Builder
        Locale.Builder localeBuilder
            = new Builder();

        // Displaying Locale.Builder
        System.out.println("LocaleBuilder: "
                           + localeBuilder);

        // setting the locale of Locale.Builder
        Locale locale = Locale.ENGLISH;
        System.out.println("Setting the Locale: "
                           + locale);

        localeBuilder
            = localeBuilder.setLocale(locale);

        // Displaying Locale.Builder
        System.out.println("Updated LocaleBuilder: "
                           + localeBuilder);
    }
}
```

**输出:**

```java
LocaleBuilder: java.util.Locale$Builder@232204a1
Setting the Locale: en
Updated LocaleBuilder: java.util.Locale$Builder@232204a1

```

**参考:**[https://docs.oracle.com/javase/9/docs/api/java/util/Locale.builder . html # setLocale-Java . util . locale-](https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Builder.html#setLocale-java.util.Locale-)