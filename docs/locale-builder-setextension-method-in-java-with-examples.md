# 场所。Java 中的 Builder setExtension()方法，示例

> 原文:[https://www . geesforgeks . org/locale-builder-set extension-method-in-Java-with-examples/](https://www.geeksforgeeks.org/locale-builder-setextension-method-in-java-with-examples/)

**[的 **setExtension()** 方法。](https://www.geeksforgeeks.org/java-util-package-java/)[场所。Java 中的 Builder 类](https://www.geeksforgeeks.org/tag/java-locale-builder/)** 用来设置这个 Locale。生成器添加到指定的扩展键。这意味着此方法将设置 Locale 的当前扩展。生成器实例来匹配所提供的扩展键和值并返回它。如果指定的扩展名为空，则删除该 LocaleBuilder 的扩展名。对照 **LDML BCP 47 兼容扩展**检查指定的扩展。

**语法:**

```java
public Locale.Builder setExtension(
                          char extensionKey, 
                          String extensionValue)

```

**参数:**此方法接受两个参数:

*   **[extension key]** : is the character value to be set to this locale > builder instance.
*   **extensionvalue** : is the string value to be set to this locale > builder instance.

**返回值:**该方法返回一个**地区。构建器实例**带有此区域设置的扩展集。生成器扩展到指定的扩展。

**异常:**此方法抛出以下异常:

*   [T0】 illformed localeexception 【T1]: If the specified extension has any malformed fields.

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

        // setting the extension of Locale.Builder
        char extensionKey = 'u';
        String extensionValue = "ca-japanese";
        System.out.println("Setting the extension: "
                           + extensionKey + "/"
                           + extensionValue);

        localeBuilder
            = localeBuilder
                  .setExtension(extensionKey,
                                extensionValue);

        // Displaying Locale.Builder
        System.out.println("Updated LocaleBuilder: "
                           + localeBuilder);
    }
}
```

**输出:**

```java
LocaleBuilder: java.util.Locale$Builder@232204a1
Setting the extension: u/ca-japanese
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

        // setting the extension of Locale.Builder
        char extensionKey = '@';
        String extensionValue = "fsdf#";
        System.out.println("Setting the extension: "
                           + extensionKey + "/"
                           + extensionValue);

        try {

            localeBuilder
                = localeBuilder
                      .setExtension(extensionKey,
                                    extensionValue);

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
Setting the extension: @/fsdf#
java.util.IllformedLocaleException:
 Ill-formed extension key:
 @ [at index 0]

```

**参考:**[https://docs.oracle.com/javase/9/docs/api/java/util/Locale.builder . html # setExtension-char-Java . lang . string-](https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Builder.html#setExtension-char-java.lang.String-)