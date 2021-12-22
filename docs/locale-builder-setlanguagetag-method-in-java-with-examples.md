# 场所。Java 中的 Builder setLanguageTag()方法，示例

> 原文:[https://www . geesforgeks . org/locale-builder-setlanguagetag-method-in-Java-with-examples/](https://www.geeksforgeeks.org/locale-builder-setlanguagetag-method-in-java-with-examples/)

**[java.util](https://www.geeksforgeeks.org/java-util-package-java/) 的 **setLanguageTag(String)** 方法。[场所。Java 中的 Builder 类](https://www.geeksforgeeks.org/tag/java-locale-builder/)** 用来重置这个 Locale。生成器添加到指定的 IETF BCP 47 语言标签中。这意味着此方法将重置 Locale 的当前状态。生成器实例来匹配所提供的语言标记并返回它。

**语法:**

```java
public Locale.Builder setLanguageTag(String languageTag)

```

**参数:**该方法接受**语言标签**作为参数，该参数是要设置到该地区的字符串。生成器实例。

**返回值:**该方法返回一个**地区。构建器实例**，这是该场所的状态。生成器设置为指定的语言标记。

**异常:**此方法抛出以下异常:

*   **ill formed locale exception** : if the specified languageTag has any fields with wrong format.

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

        // setting the languageTag
        // of Locale.Builder
        String languageTag = "FRENCH";
        System.out.println("Setting the language: "
                           + languageTag);

        localeBuilder
            = localeBuilder
                  .setLanguageTag(languageTag);

        // Displaying Locale.Builder
        System.out.println("Updated LocaleBuilder: "
                           + localeBuilder);
    }
}
```

**输出:**

```java
LocaleBuilder: java.util.Locale$Builder@232204a1
Setting the language: FRENCH
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

        // setting the languageTag
        // of Locale.Builder
        String languageTag = "asdasf@!vsd#";
        System.out.println("Setting the languageTag: "
                           + languageTag);

        try {
            localeBuilder
                = localeBuilder
                      .setLanguageTag(languageTag);

            // Displaying Locale.Builder
            System.out.println("Updated LocaleBuilder: "
                               + localeBuilder);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
LocaleBuilder: java.util.Locale$Builder@232204a1
Setting the languageTag: asdasf@!vsd#
java.util.IllformedLocaleException: Invalid subtag: asdasf@!vsd# [at index 0]

```

**参考:**[https://docs.oracle.com/javase/9/docs/api/java/util/Locale.builder . html # setLanguageTag-Java . lang . string-](https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Builder.html#setLanguageTag-java.lang.String-)