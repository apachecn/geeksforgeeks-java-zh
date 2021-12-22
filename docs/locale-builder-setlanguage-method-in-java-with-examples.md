# 场所。Java 中的 Builder setLanguage()方法，带示例

> 原文:[https://www . geesforgeks . org/locale-builder-set language-method-in-Java-with-examples/](https://www.geeksforgeeks.org/locale-builder-setlanguage-method-in-java-with-examples/)

**[java.util](https://www.geeksforgeeks.org/java-util-package-java/) 的 **setLanguage(String)** 方法。[场所。Java 中的 Builder 类](https://www.geeksforgeeks.org/tag/java-locale-builder/)** 用来设置这个 Locale。生成器转换为指定的语言。这意味着此方法将设置 Locale 的当前语言。生成器实例来匹配所提供的语言并返回它。如果指定的语言为 null 或空，则删除该 LocaleBuilder 的语言。

**语法:**

```
public Locale.Builder
  setLanguage(String language)

```

**参数:**该方法接受**语言**作为参数，该参数是要设置到该地区的字符串。生成器实例。

**返回值:**该方法返回一个**地区。构建器实例**使用该地区的语言。生成器设置为指定的语言。

**异常:**此方法抛出以下异常:

*   **ill formed locale exception** : If the specified language has any improperly formatted fields,

**程序 1:**

```
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

        // setting the language of Locale.Builder
        String language = "FRENCH";
        System.out.println("Setting the language: "
                           + language);

        localeBuilder
            = localeBuilder.setLanguage(language);

        // Displaying Locale.Builder
        System.out.println("Updated LocaleBuilder: "
                           + localeBuilder);
    }
}
```

**输出:**

```
LocaleBuilder: java.util.Locale$Builder@232204a1
Setting the language: FRENCH
Updated LocaleBuilder: java.util.Locale$Builder@232204a1

```

**程序二:**

```
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

        // setting the language of Locale.Builder
        String language = "asdasf@!vsd#";
        System.out.println("Setting the language: "
                           + language);

        try{
        localeBuilder
            = localeBuilder.setLanguage(language);

        // Displaying Locale.Builder
        System.out.println("Updated LocaleBuilder: "
                           + localeBuilder);
                           }
        catch(Exception e)
        {
            System.out.println(e);
            }
    }
}
```

**输出:**

```
LocaleBuilder: java.util.Locale$Builder@232204a1
Setting the language: asdasf@!vsd#
java.util.IllformedLocaleException: Ill-formed language: asdasf@!vsd# [at index 0]

```

**参考:**[https://docs.oracle.com/javase/9/docs/api/java/util/Locale.builder . html # setLanguage-Java . lang . string-](https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Builder.html#setLanguage-java.lang.String-)