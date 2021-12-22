# 场所。Java 中的 Builder setVariant()方法，示例

> 原文:[https://www . geesforgeks . org/locale-builder-set variant-method-in-Java-with-examples/](https://www.geeksforgeeks.org/locale-builder-setvariant-method-in-java-with-examples/)

**[的 **setVariant(String)** 方法。](https://www.geeksforgeeks.org/java-util-package-java/)[场所。Java 中的 Builder 类](https://www.geeksforgeeks.org/tag/java-locale-builder/)** 用来设置这个 Locale。生成器转换为指定的变量。这意味着此方法将设置 Locale 的当前变体。生成器实例来匹配所提供的变量并返回它。如果指定的变量为空，则删除该 LocaleBuilder 的变量。根据 IETF BCP 47 变体子标签的语法要求检查指定的变体，之后将其规范化为小写。

**语法:**

```
public Locale.Builder setVariant(String variant)

```

**参数:**该方法接受**变量**作为参数，该参数是要设置到该地区的字符串。生成器实例。

**返回值:**该方法返回一个**地区。构建器实例**具有此区域设置的变体集。生成器转换为指定的变量。

**异常:**此方法抛出以下异常:

*   [T0】 illformed localeexception 【T1]: If the specified variable has any fields with wrong format,

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

        // setting the variant of Locale.Builder
        String variant
            = (new Locale("nu", "NO", "NY"))
                  .getDisplayVariant();
        System.out.println("Setting the variant: "
                           + variant);

        localeBuilder
            = localeBuilder.setVariant(variant);

        // Displaying Locale.Builder
        System.out.println("Updated LocaleBuilder: "
                           + localeBuilder);
    }
}
```

**输出:**

```
LocaleBuilder: java.util.Locale$Builder@232204a1
Setting the variant: Nynorsk
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

        // setting the variant of Locale.Builder
        String variant = "asdasf@!vsd#";
        System.out.println("Setting the variant: "
                           + variant);

        try{
        localeBuilder
            = localeBuilder.setVariant(variant);

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
Setting the variant: asdasf@!vsd#
java.util.IllformedLocaleException:
 Ill-formed variant:
 asdasf@!vsd# [at index 0]

```

**参考:**[https://docs.oracle.com/javase/9/docs/api/java/util/Locale.builder . html # setVariant-Java . lang . string-](https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Builder.html#setVariant-java.lang.String-)