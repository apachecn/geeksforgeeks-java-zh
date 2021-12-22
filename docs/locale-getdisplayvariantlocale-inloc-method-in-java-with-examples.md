# Java 中的 Locale getDisplayVariant(Locale inLoc)方法，示例

> 原文:[https://www . geesforgeks . org/locale-getdisplayvariantloceale-inloc-method-in-Java-with-examples/](https://www.geeksforgeeks.org/locale-getdisplayvariantlocale-inloc-method-in-java-with-examples/)

Java 中 **[Locale 类](https://www.geeksforgeeks.org/java-util-locale-class-java-set-1/)** 的**getDisplayVariant(Locale inLoc)**方法用于获取指定区域中提到的区域的变体代码的名称，并适当地显示给用户。如果区域设置中没有提到变体代码，该函数将返回一个空字符串。

**语法:**

```
public String getDisplayVariant(Locale inLoc)
```

**参数:**该方法取 Locale 类型的一个参数 *inLoc* ，指名称的本地化显示。

**返回值:**这个方法返回适合给定区域设置的显示语言的名称。

**异常:**如果参数 inLoc 为空，则方法抛出 **[空指针异常](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)** 。

以下程序说明了 getDisplayVariant()方法的工作:
**程序 1:**

```
// Java code to illustrate getDisplayVariant() method

import java.util.*;

public class Locale_Demo {
    public static void main(String[] args)
    {

        // Creating a new locale
        Locale first_locale
            = new Locale("th", "TH", "TH");

        // Displaying first locale
        System.out.println("First Locale: "
                           + first_locale);

        // Displaying the variant code for locale
        System.out.println("Variant: "
                           + first_locale.getDisplayVariant(
                                 new Locale("fr", "French")));
    }
}
```

**Output:**

```
First Locale: th_TH_TH_#u-nu-thai
Variant: TH

```

**程序 2:**

```
// Java code to illustrate getDisplayVariant() method

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

        // Displaying the variant code for locale
        System.out.println("Variant: "
                           + first_locale.getDisplayVariant(
                                 new Locale("fr", "French")));
    }
}
```

**Output:**

```
First Locale: en_US
Variant:

```

**参考:**[https://docs . Oracle . com/javae/7/docs/API/Java/util/locale . html # getdisplayvariant(Java . util . locale)](https://docs.oracle.com/javase/7/docs/api/java/util/Locale.html#getDisplayVariant(java.util.Locale))