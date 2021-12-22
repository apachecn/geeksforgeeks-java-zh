# 场所。Java 中的 Builder build()方法，示例

> 原文:[https://www . geesforgeks . org/locale-builder-build-method-in-Java-with-examples/](https://www.geeksforgeeks.org/locale-builder-build-method-in-java-with-examples/)

**建()**法 **[爪哇](https://www.geeksforgeeks.org/java-util-package-java/)。[场所。Java 中的 Builder 类](https://www.geeksforgeeks.org/tag/java-locale-builder/)** 用于从指定给这个 Locale 的值中构建一个 Locale。生成器实例。此方法在构建后返回一个 Locale 实例。

**语法:**

```java
public Locale build()

```

**参数:**此方法不接受任何参数。

**返回类型:**该方法返回一个 **[区域设置](https://www.geeksforgeeks.org/java-util-locale-class-java-set-1/)** 实例，该实例的值设置为 Locale.Builder。

**异常:**这个方法不抛出任何异常。

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

        // setting the locale of Locale.Builder
        Locale locale = Locale.FRANCE;
        System.out.println("Setting the Locale: "
                           + locale);
        localeBuilder.setLocale(locale);

        // Displaying Locale.Builder
        System.out.println("LocaleBuilder: "
                           + localeBuilder);

        // Building the Locale from Locale.Builder
        System.out.println("Building the Locale.");

        Locale builtLocale = localeBuilder.build();

        // Displaying Locale.Builder
        System.out.println("Built Locale: "
                           + builtLocale);
    }
}
```

**输出:**

```java
Setting the Locale: fr_FR
LocaleBuilder: java.util.Locale$Builder@232204a1
Building the Locale.
Built Locale: fr_FR

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

        // setting the locale of Locale.Builder
        Locale locale = Locale.ENGLISH;
        System.out.println("Setting the Locale: "
                           + locale);
        localeBuilder.setLocale(locale);

        // Displaying Locale.Builder
        System.out.println("LocaleBuilder: "
                           + localeBuilder);

        // Building the Locale from Locale.Builder
        System.out.println("Building the Locale.");

        Locale builtLocale = localeBuilder.build();

        // Displaying Locale.Builder
        System.out.println("Built Locale: "
                           + builtLocale);
    }
}
```

**输出:**

```java
Setting the Locale: en
LocaleBuilder: java.util.Locale$Builder@232204a1
Building the Locale.
Built Locale: en

```

**参考:**[https://docs.oracle.com/javase/9/docs/api/java/util/Locale.builder . html # build–](https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Builder.html#build--)