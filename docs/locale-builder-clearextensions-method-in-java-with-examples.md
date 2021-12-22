# 场所。Java 中的 Builder clearExtensions()方法，示例

> 原文:[https://www . geesforgeks . org/locale-builder-clear extensions-method-in-Java-with-examples/](https://www.geeksforgeeks.org/locale-builder-clearextensions-method-in-java-with-examples/)

**[的 **clearExtensions()** 方法。](https://www.geeksforgeeks.org/java-util-package-java/)[场所。Java 中的 Builder 类](https://www.geeksforgeeks.org/tag/java-locale-builder/)** 用来重置这个 Locale。生成器对其初始和空状态的扩展。通过此方法，语言、脚本、变体和区域的所有其他值保持不变。

**语法:**

```java
public Locale.Builder clearExtensions()

```

**参数:**此方法不接受任何参数。

**返回类型:**该方法返回一个**地区。带有扩展的构建器实例**重置为其初始和空状态。

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

        // Displaying Locale.Builder
        System.out.println("LocaleBuilder: "
                           + localeBuilder);

        // clearing the extensions
        // of Locale.Builder
        System.out.println("Clearing the"
                           + " extensions.");

        localeBuilder
            = localeBuilder.clearExtensions();

        // Displaying Locale.Builder
        System.out.println("Updated LocaleBuilder: "
                           + localeBuilder);
    }
}
```

**输出:**

```java
LocaleBuilder: java.util.Locale$Builder@232204a1
Clearing the extensions.
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

        localeBuilder
            = localeBuilder
                  .setExtension('u',
                                "ca-japanese");

        // Displaying Locale.Builder
        System.out.println("Extension set "
                           + "of LocaleBuilder: "
                           + localeBuilder);

        // clearing the extensions
        // of Locale.Builder
        System.out.println("Clearing the"
                           + " extensions.");

        localeBuilder
            = localeBuilder.clearExtensions();

        // Displaying Locale.Builder
        System.out.println("Updated LocaleBuilder: "
                           + localeBuilder);
    }
}
```

**输出:**

```java
LocaleBuilder: java.util.Locale$Builder@232204a1
Extension set of LocaleBuilder: java.util.Locale$Builder@232204a1
Clearing the extensions.
Updated LocaleBuilder: java.util.Locale$Builder@232204a1

```

**参考:**[https://docs.oracle.com/javase/9/docs/api/java/util/Locale.builder . html # ClearExtensions–](https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Builder.html#clearExtensions--)