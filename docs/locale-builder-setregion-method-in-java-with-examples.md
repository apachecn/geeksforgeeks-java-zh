# 场所。Java 中的 Builder setRegion()方法，示例

> 原文:[https://www . geesforgeks . org/locale-builder-set region-method-in-Java-with-examples/](https://www.geeksforgeeks.org/locale-builder-setregion-method-in-java-with-examples/)

**设置区域(字符串)**的方法 **[java.util](https://www.geeksforgeeks.org/java-util-package-java/) 。[场所。Java 中的 Builder 类](https://www.geeksforgeeks.org/tag/java-locale-builder/)** 用来设置这个 Locale。生成器添加到指定区域。这意味着此方法将设置当前区域设置。生成器实例来匹配所提供的区域并返回它。如果指定的区域为空，则该区域将被删除。格式良好的区域值包括由 ISO 3166 标准定义的 **2 个字母的区域代码或 3 位联合国 M.49 区号**。

**语法:**

```java
public Locale.Builder setRegion(String region)

```

**参数:**该方法接受**区域**作为参数，该参数是要设置到该地区的字符串。生成器实例。

**返回值:**该方法返回一个**地区。构建器实例**具有此区域设置的区域。生成器添加到指定区域。

**异常:**此方法抛出以下异常:

*   [T0】 illformed localeexception 【T1]: If there are any fields with incorrect format in the specified area,

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

        // setting the region of Locale.Builder
        String region = "IN";
        System.out.println("Setting the region: "
                           + region);

        localeBuilder
            = localeBuilder.setRegion(region);

        // Displaying Locale.Builder
        System.out.println("Updated LocaleBuilder: "
                           + localeBuilder);
    }
}
```

**输出:**

```java
LocaleBuilder: java.util.Locale$Builder@232204a1
Setting the region: IN
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

        // setting the region of Locale.Builder
        String region = "asdasf@!vsd#";
        System.out.println("Setting the region: "
                           + region);

        try {
            localeBuilder
                = localeBuilder.setRegion(region);

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
Setting the region: asdasf@!vsd#
java.util.IllformedLocaleException:
 Ill-formed region:
 asdasf@!vsd# [at index 0]

```

**参考:**[https://docs.oracle.com/javase/9/docs/api/java/util/Locale.builder . html # setRegion-Java . lang . string-](https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Builder.html#setRegion-java.lang.String-)