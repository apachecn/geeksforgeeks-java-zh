# 区域设置默认值(区域设置。Java 中的类别、区域设置)方法，示例

> 原文:[https://www . geesforgeks . org/locale-setdefaultlocale-category-locale-method-in-Java-with-examples/](https://www.geeksforgeeks.org/locale-setdefaultlocale-category-locale-method-in-java-with-examples/)

**设置默认值(*区域设置。类别 cate，Locale newLoc*)**[Java 中的 Locale 类](https://www.geeksforgeeks.org/java-util-locale-class-java-set-1/)** 的**方法用于设置 JVM 或 Java 虚拟机的这个实例的默认区域设置，这丝毫不会影响区域设置主机。

**语法:**

```
public static void 
    setDefault(Locale.Category cate,  
               Locale newLocale)
```

**参数:**该方法取两个参数:

*   **美食:**这是本地的。类别类型，并指定默认区域设置要设置到的类别。
*   **newLoc:** 这也是区域设置类型，指的是新的默认区域设置。

**返回值:**该方法不返回值。

**异常:**该方法可以抛出如下异常-

*   **SecurityException:** 如果安全管理器存在，并且其 checkPermission 方法不允许该操作，则会引发此问题。
*   **[null pointerexception](https://www.geeksforgeeks.org/null-pointer-exception-in-java/):**如果 newLoc 为空，则抛出此异常。

下面的程序说明了区域设置类的 setDefault()方法:
**示例 1:**

```
// Java code to illustrate setDefault() method

import java.util.*;

class Locale_Demo {
    public static void main(String[] args)
    {

        // Creating a new locale
        Locale first_locale
            = new Locale("nu", "NO", "NY");

        // Displaying first locale
        System.out.println("First Locale: "
                           + first_locale);

        // Setting the Locale
        Locale.setDefault(Locale.Category.DISPLAY,
                          new Locale("ar", "SA"));

        Locale new_locale = Locale.getDefault();

        // Displaying the default locale of new locale
        System.out.println("The default locale: "
                           + new_locale);
    }
}
```

**输出:**

```
First Locale: nu_NO_NY
The Hash Code: en_US

```

**例 2:**

```
// Java code to illustrate setDefault() method

import java.util.*;

class Locale_Demo {
    public static void main(String[] args)
    {

        // Creating a new locale
        Locale first_locale
            = new Locale("en", "IN");

        // Displaying first locale
        System.out.println("First Locale: "
                           + first_locale);

        // Setting the Locale
        Locale.setDefault(Locale.Category.FORMAT,
                          new Locale("en", "US"));

        Locale new_locale = Locale.getDefault();

        // Displaying the default locale of new locale
        System.out.println("The default locale: "
                           + new_locale);
    }
}
```

**输出:**

```
First Locale: en_IN
The Hash Code: en_US

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/locale . html # getDefault–](https://docs.oracle.com/javase/9/docs/api/java/util/Locale.html#getDefault--)